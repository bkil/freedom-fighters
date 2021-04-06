# IaaS szerverek tesztelése

## Cél

Egy VPS közös erőforrásokra épül. Azért adhatják egy dedikált fizikai hardverhez képes törtrész áron ([cheap-cheap-server-hosting.md](cheap-server-hosting.md)), mivel a felhasználók nem használják ki minden pillanatban minden erőforrásukat. Sőt - a gépek jelentős része általában tétlen állapotban várja a kéréseket.

### CPU megosztás

Emiatt az megszokott, hogy egy szolgáltató az adott szerverén több VPS vCPU magot adjon el, mint amivel a gép fizikailag rendelkezik és azt minden időpillanatban igazságosan osztja el az igényekhez mérten. 2-3x túlfoglalás jónak számít, de régen a legolcsóbb akciós helyeken nem volt ritka a 10-20x arány sem.

### Tárhely és memória megosztás

Ellenben a háttértár területe és a munkamemória tipikusan dedikált szokott lenni, hogy az minden pillanatban rendelkezésre álljon.

OpenVZ alatt néha engedélyezik a "burstable RAM" rendelkezésre állását is, aminek segítségével folyamataink rövid időtartamra a garantáltnál egy bizonyos százalékkal többet is felhasználhatnak azok kényszerített leállítása előtt.

### CPU dedikáció

Bizonyos szolgáltatók bizonyos csomagjaikban biztosíthatnak adott arányú VPS vCPU dedikációt, azaz hogy minden pillanatban legalább 0.5-1 vCPU teljes számítási kapacitását szabadon tartják a számunkra.

Ennél a valamivel költségesebb úgynevezett "dedicated" szerverek esetén garantálják a specifikáció teljes dedikációját (ideálisan az egész gépet) amivel biztosítják a kiszámíthatóan alacsony ütemezői késleltetést például VoIP vagy játékszerverek számára.

## Eszközök

Az alábbi elérések alaplap és CPU típustól és beállítástól függően eltérhetnek. Érdemes ide összegyűjteni a gyakori alternatívákat.

### Virtualizációs technológia

```
apt install virt-what &&
virt-what
```

### Benchmark

```
apt install curl &&
wget -qO- yabs.sh | bash -s -- -r
```

### CPU

#### cpuinfo

* Hány mag (szál) található egy foglalatban: `siblings`
* Mennyi gyorsítótár van benne: `cache size`
* Milyen utasításkészletet tud: `flags`

```
cat /proc/cpuinfo
```

#### cpuinfo_max_freq

* Mekkora órajelre képes pillanatnyi turbóban?

```
cat /sys/devices/system/cpu/cpufreq/policy0/cpuinfo_max_freq
```

#### scaling_cur_freq

* Mekkora órajelre képes ha sok mag le van terhelve

```
grep '' /sys/devices/system/cpu/cpufreq/policy*/scaling_cur_freq
```

#### Szálak

* Hány CPU szál van a gépházban, foglalatokkal felszorozva.
* Lásd még: [#dmidecode](#dmidecode)

```
ls -d /sys/devices/system/cpu/cpu[0-9]* | wc -l
```

#### loadavg

* A szálakhoz mérten hány folyamat áll sorban?
* Ideális, ha kevesebb mint 50%.

```
cat /proc/loadavg
```

### dmidecode

* RAM: méret, technológia, sávszélesség, több csatornás, ECC
* Redundáns-e a hálókártya, tápegység?

```
sudo apt install dmidecode &&
dmidecode | less
```

#### lshw

Több eszköz kimenetének összefoglaló nézete.

```
sudo apt install lshw &&
lshw | less
```

### PCIe hardverelemek

Nem mindig mond többet mint a [#dmidecode](#dmidecode), de nevesítve feloldja amire az csak számokkal hivatkozik, például a hálózati kártya típusát. Előfordulhat, hogy mondjuk a háttértár típusa is felfedezhető vele.

```
sudo apt install pciutils &&
lspci -nn
```

### USB hardverelemek

Szerverekben nem gyakori.

```
sudo apt install lsusb &&
lsusb &&
lsusb -t
```

### Memória

* Ennek összege is kiadja látszólag a gép kapacitását
* Lásd még: [#dmidecode](#dmidecode)

```
grep "^DirectMap" /proc/meminfo
```

#### vSwap

Ezt tipikusan nem háttértáron alakítják ki, hanem virtuálisan lassított RAM-on.

```
free
cat /proc/swaps
```

### Hűtés

* Jól klimatizált-e a helyiség vagy fog throttle-özni nyáron terhelés mellett?

```
grep '' /sys/class/thermal/thermal_zone*/*temp* 2>/dev/null
grep '' /sys/devices/pci0000:00/0000:00*/0000*/hwmon/hwmon*/* 2>/dev/null
grep '' /sys/devices/platform/coretemp.*/hwmon/hwmon*/temp*_{label,input} | sort
```

### Hálózat

Bár mivel a legtöbb forgalom le van választva ezért nem láthatjuk közvetlenül a hálózat leterheltségét, a multicast és broadcast csomagok hozzánk is megérkeznek monitor módban. Ezekből a többiek nevére, címére és néhány ellenoldali címre is lehet következtetni. Ilyenek például:

* ARP IP címfeloldás
* 802.1d STP útkeresés (spanning tree protocol)
* CDPv1 Cisco switch felismerés
* DHCP címkérés
* IPv6 szomszédságfelfedezés
* SSDP
* SMB

```
sudo apt install net-tools tcpdump tshark iftop
route -n
tcpdump -vni eth0 "not host SshKliensemCime" # vagy: "not tcp"
tshark -nVx "not tcp"
iftop
```

### Tárhely

* Mennyi helyünk van
* Mekkora a teljes lemez (`sda` vagy `dm-*`)
* Hány `loop` eszköz van, hányan osztoznak a gépen

```
df /
cat /proc/partitions
ls /proc/fs/ext4/loop*/mb_groups | wc -l
```

## Kihasználtsági becslés

A fenti csatolások és a szolgáltató árlistája alapján meg tudjuk becsülni, hogy a felhasználók mekkora részesedést szereznek fajlagosan memória, tárhely és CPU tekintetében. Itt egy példa számítás, ki lehetne indulni a `partitions` vagy más alapján is:

```
wc -l /proc/fs/ext4/loop*/mb_groups |
head -n -1 |
awk '{print ($1 - 1) / 8}' |
sed "
s~^5$~& 1 0.5 450~; t e
s~^10$~& 1 1 450~; t e
s~^20$~& 1 2 790~; t e
s~^40$~& 2 4 1580~; t e
s~^60$~& 3 8 2890~; t e
s~^80$~& 4 16 3590~; t e
s~^120$~& 6 20 5600~; t e
s~^180$~& 8 32 9300~; t e
:e" |
awk '
  {
    s += $1;
    c += $2;
    r += $3;
    f += $4;
    print
  }
  END {
    print "= " s " GB HDD, " c " vCPU, " r " GB RAM, " f " HUF/month"
  }' |
sort |
uniq -c |
sort -n
```
