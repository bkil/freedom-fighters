# Legolcsóbb szerverszolgáltatások

## Javaslatok

Tipikusan tesztelési vagy egyszemélyes felhasználásra.

Az ötlet, hogyha egy informatikában kicsit jártasabb ismerősünk meglátja a magunk által üzemeltetett szabad szoftveres alternatívákra mutató linkjeinket akkor tudjunk kérésre neki is egy konkrét szolgáltatót és árat ajánlani, illetve egy kattintásos telepítési utasítást. Ezt akár egy kis szöveges bannerrel is megtehetjük minden oldalunk alján.

Az alapvetés, hogy normál felhasználásra KVM/Xen-es gépek legalább félig dedikált magokkal, SSD-vel, biztonsági mentéssel ajánlhatók. Minden más (OpenVZ, LXC, üresjáratból szétosztott CPU, HDD) főleg csak próbálkozásra vagy nagyon minimális és CDN útján gyorsítótárazott szolgáltatásokra javasolt amit egyszerre csak 1-2 felhasználó fog megnyitni.

Amennyiben kiszemeltünk egy ilyet és van erre lehetőség, érdemes olyan helyet keresni ahol vannak nagyobb, de még mindig jó ár-érték arányú csomagok és biztosított a próbahónap vagy rövid távú fizetős konstrukció is, hogyha kevésnek találjuk a teljesítményt, tudjunk bővíteni.

Érdemes az alábbi szempontokat is figyelembe venni:

* [iaas-testing.md](iaas-testing.md)

### LXC és OpenVZ alatt nem megy

* Egyedi operációs rendszer telepítés (csak sablonból)
* Saját kernel fordítás, hangolás
* Kernel frissítés
* Nem alapértelmezett kernel modulok betöltése vagy paraméterezése
* A legtöbb sysctl
* Docker
* ??? Docker + systemd-nspawn (amennyiben `sysctl kernel.unprivileged_userns_clone` = 1)
* OpenVPN vagy IPv6 tunnel (TUN/TAP engedélyezése vagy annak kérelmezése szüksége a VPS-re)
* IPsec (net_admin képesség és néhány kernel modulnak be kell lennie töltve)
* Bizonyos architektúra-implementáció specifikus biztonsági áthallás elleni védelmek
* /dev/loopN
* Titkosított kötetek
* Pontos idő beállítása
* swap (vagy RAM-ban vswap) csak ha engedélyezték és fix méretű

### LXC és OpenVZ alatt is megy

* iptables tűzfal beállítások, ipset
* Csomagtelepítés
* PPP alapú VPN (PPTP/L2TP)
* WireGuard-go
* ssh tunnel, ssh socks proxy
* FUSE
* OpenVZ alatt LXC konténerek indítása

### LXC és OpenVZ előnyei

* Erőforrás bővítéshez nem kell leállítani
* Nagyon gyors boot
* Kicsit több memória áll rendelkezésre: bájtra pontosan annyit foglalhatunk le folyamatainkkal mint a specifikációban szerepel, mivel nem jön le belőle kernel vagy BIOS által félretett terület a lemezpuffereken felül

## Magyarok

Itt az lenne a koncepció, hogy a személyes adataink ne hagyják el az országot.

_TODO: Ideálisan utána kéne járni egyenként, hogy kinek hol vannak a szerverei._

### Legolcsóbb magyarok

* https://ugyfelkapu.hostingbazis.hu/aff.php?aff=142 301 + áfa (383, 1 év)
  * **LXC VPS Micro**, LXC, 1 vCPU (HP ProLiant DL360e Gen8, 2 * E5-2430L v2 @ 2.6-2.8GHz), 1GB RAM (DDR3 ECC), 10GB SSD (SAS RAID10), 1GB vSwap, 8 napi mentés, korlátlan adatforgalom, 1Gb/s, IPv4 + /128 IPv6 (tesztelve magyar: SzerverPlex.hu Kft. Budapest, 1132 Victor Hugo utca 18-22)
  * fizetés: Stripe bankkártya, banki átutalás, OTP bankfiók befizetés, PayPal checkout, PayPal fizetés
  * bejelentkezés: egy kattintásos reCAPTCHA
* https://rackoonet.hu/openvz-7-vps/ 417 (1 év, alanyi adómentes)
  * **OVZ7-START (2020)**: OpenVZ 7, 1 vCPU (HP DL380, 2x Intel Xeon 6-core +HT, 3GHz), 512MB RAM, 5GB HDD (6x HP 10k SAS, HP HW RAID10 + FBWC), korlátlan adatforgalom, 200Mb/s, IPv4 (elvileg magyar: Victor Hugo 18-22)
* https://atw.hu/vps 445 + áfa (2 év)
  * **egyéni VPS konfigurátor**, KVM, 1 vCPU, 512MB RAM, 5GB SSD (DRBD mirror), 1Gb/s, IPv4 + /56 IPv6 (magyar: Victor Hugo 11-15, 18-22)
  * cég: magyar; ATW Internet Kft.; H-1138 Budapest, Esztergomi út 66. fsz. 1.; Adószám: 13471868-2-41; Cégjegyzékszám: 01-09-736956
* https://vps4you.hu/r/vives 699 Ft/hó vagy 6962 Ft/év (alanyi adómentes)
  * **SSD VPS 512MB**, KVM, 1 vCPU (Dell C6100, Intel Xeon CPU X5650 @ 2.67GHz), 512MB RAM (DDR3 ECC), 5GB SSD (ZFS SSD RAID), ~30TB/hó adatforgalom (<100Mb/s), 1Gb/s (2*1Gb/s szerverenként), IPv4 + /128 IPv6 (magyar: DENINET Kft 1132 Budapest, Victor Hugo 18-22)
  * 3 nap tesztelés ingyen
  * Előfizetéskor +1 hónap ingyen kuponkód: `Firstimer2021`
  * Előfizetéskor bérleti idő duplázáshoz Ryzen 3900X NVME VPS kuponkód: `RYZEN02`
* https://szerverplex.hu/virtualis-szerver-berles/ 672 + áfa (1 év)
  * **KVM VPS 1/1/10 HDD 2020**, KVM, 1 vCPU (HP DL580 4x Intel E7 szériás 8-10 magos), 1GB RAM (DDR3 ECC), 10GB HDD (HP SAS 6G, 10K RPM, HW RAID10, FBWC), korlátlan adatforgalom, 1Gb/s (garantált 20% belföld, 5% külföld, 10Gb/s szerverenként), IPv4 + /128 IPv6 (elvileg magyar: Victor Hugo 18-22)
* https://xethost.hu/vps-berles/ 890 + áfa
  * **Linux Cole**, VMware ESXi?, 1 vCPU (2.0GHz, E5-2530 v4?), 512MB RAM, 10GB SSD, korlátlan adatforgalom, 100Mb/s, IPv4 + /128 IPv6 (elvileg magyar: Victor Hugo 18-22)

### Normál árú magyarok

* http://szervernet.hu/vps 1000 + áfa
  * **Xencloud Small**, Xen, 1 vCPU, 1GB RAM, 20GB HDD, korlátlan adatforgalom, IPv4 (tesztelve magyar: Victor Hugo 18-22)
* https://www.mikrovps.net/hu/vps/lxc 1000 + áfa
  * **LXC-1G**, LXC, 1 vCPU (Xeon E5), 1GB RAM, 20GB SSD, 1-5TB adatforgalom, 10Gb/s, IPv4 + /128 IPv6 (elvileg magyar, DoclerWeb 1101 Budapest, Expo tér 5-7?)
* https://www.mhosting.hu/vps/ssd-vps 1000 + áfa
  * **SSD VPS - 0.5**, KVM, 1 vCPU (Dell PowerEdge, 6-magos Xeon 3.3-4.0GHz), 512MB RAM (DDR3 ECC), 15GB SSD, korlátlan adatforgalom, 1Gb/s (5Gb/s BIX uplink, 500Mb/s nemzetközi), IPv4 (elvileg magyar: Victor Hugo 18-22)
* https://www.seedworld.hu/vps.html 1000 + áfa (1270)
  * **VPS Start**, 1 vCPU, 1GB RAM, 15GB HDD, korlátlan adatforgalom, 100Mb/s (talán magyar: szerverpark.eu Victor Hugo 11-15)
* https://clans.hu/vps-standard 1000 + ?
  * **VPS Standard S**: KVM, 2 vCPU (INTEL XEON E5-2450 MAX 2.30 GHZ), 2GB RAM (DDR3 1600MHz), 10GB SSD (NVMe RAID), korlátlan adatforgalom, 100/100Mb/s, IPv4 (elvileg magyar, de ismeretlen helyen)
* https://vgh.hu/linux_vps 1250 (alanyi adómentes)
  * **HDD 1024**, VMWare, 1 vCPU, 1GB RAM, 20GB HDD, korlátlan adatforgalom, IPv4
* https://client.ezit.hu/cart.php?a=add&pid=477 1083 + áfa (1 év) (régi nevükön: cloud.hu)
  * **Neo Cloud VPS+ 1-1-25**, KVM, 1 vCPU (Dell PowerEdge, 6 magos Xeon), 1GB RAM, 25GB SSD (RAID), korlátlan adatforgalom, 100Mb/s (2 * 1Gb/s szerverenként, 2 * 10Gb/s BIX, 2 * 10Gb/s nemzetközi, 1 * 3Gb/s magyar), IPv4 (elvileg magyar: Victor Hugo 18-22)
* https://szerverpark.eu/vps 1250 + áfa (1 év)
  * **VPS START**, 1 vCPU, 1GB RAM, 15GB HDD, korlátlan adatforgalom, 100Mb/s (elvileg magyar: Victor Hugo 11-15)
* http://www.profivps.hu/vps 1260 + áfa (1600)
  * **Magyar VPS minimál**, OpenVZ (kérésre teljes virtualizáció), 2 vCPU (1500MHz), 512MB RAM, 10GB HDD (SAS), korlátlan adatforgalom, 1 IPv4 + 5 IPv6 (elvileg magyar: DENINET Kft -> Victor Hugo 18-22)
* https://jztkft.hu/vpshosting.php#level-1-0 1500 + ?
  * **Linux VPS Mini**, Xen, 1 vCPU (Intel Xeon X5675), 2GB RAM (DDR3L 1333MHz ECC), 20GB HDD (WD Gold Enterprise, Dell Raid10), korlátlan adatforgalom, 1Gb/s (10Gb/s szerverenként), IPv4 + /128 IPv6 (elvileg magyar: Victor Hugo 18-22)
* https://rackforest.com/szolgaltatasok/vps/#linux-vps 1500 + áfa
  * **Linux VPS One**, KVM, 1 vCPU (Xeon E5), 1GB RAM, 20GB SSD, 10Gb/s (2Gb/s garantált), 30TB/hó adatforgalom (efölött 100Mb/s korlátlan), IPv4 + /56 IPV6 kérésre (elvileg magyar: Dataneum Kozma utca 2, Victor Hugo 18-22, Dataplex Asztalos Sándor utca 13)

## Nemzetközi

Néhány lehetséges ok ami érdekessé teheti az itt megemlítetteket (nem mindenkire igaz mind):

* az abszolút legolcsóbbak
* sok éves múltra tekintenek vissza
* megbízhatók privacy szempontból
* másoknak is ajánlható  szabad szoftveres tömegigényt elégíthetnek ki
  * sima jelenlét
  * vagy extra tárhelyet nyújtanak biztonsági mentésnek vagy videóknak
  * vagy jelentős havi adatátvitelt biztosítanak

### Akciók

Itt rendszeresen osztanak meg akciókat egymással a tagok:

* https://lowendbox.com/

### Nemzetközi példák minimális jelenlétre

* https://clients.inceptionhosting.com/cart.php?gid=22 "OpenVZ UK OVZ512", OpenVZ 7, IPv4 + /64 IPv6, 512MB RAM, 15GB HDD, 500GB/hó forgalom, 1.17 EUR/hó
* https://hosting.gullo.me/order/main/packages/nat-ipv4-vps-de/?group_id=5 OpenVZ 7, NAT (20 port + 1 SSH port) + /80 IPv6, 128MB RAM, 3GB HDD, 125GB/hó forgalom, 0.29 USD/hó

* https://hax.co.id/ ingyen, NAT IPv4 + /112 IPv6, korlátlan forgalom, Telegram fiók szükséges, 30 naponta megújítandó

Itt egy másik jegyzetünk ami arra koncentrált, hogy hol lehet hónapokig, évekig vagy akár korlátlanul teljesen ingyen szervert futtatni, de ezek tipikusan nem etikus szolgáltatók:

* https://gitlab.com/bkil/hardware/-/blob/master/doc/hu/free-cloud.md

### Nemzetközi példák normál felhasználásra

* https://www.arubacloud.hu/vps/virtualis-privat-szerver-ajanlat-tipusok.aspx 900 + áfa
  * **Cloud VPS Small**, VMWare, 1 vCPU, 1GB RAM, 20GB SSD, 2TB/hó adatforgalom, IPv4 + /64 IPv6
* https://www.hetzner.com/sb pl. dedicated: core i7-2600 2x4TB HDD 16GB RAM 34 EUR/hó
* https://www.kimsufi.com/en/servers.xml KS-3 Atom 2c/4t 1.86GHz, 4GB RAM, 2TB HDD, 100 Mb/s, Franciaország/Kanada, IPv4 + /128 IPv6, 8 EUR/hó+áfa
* https://contabo.com/en/vps/ 4 vCPU, 8GB RAM, 200GB SSD, 200 Mb/s, Németország, IPv4 + /64 IPv6, 5 EUR/hó
* https://www.time4vps.com/linux-vps/ Litvánia (Vilnus), KVM, 100 Mb/s hálózat, IPv4 + /128 IPv6 (kérésre több)
  * **Linux 2**: 4 EUR/hó, 1 vCPU (2.6GHz, Intel Xeon Gold 6132), 2GB RAM (DDR4-2666 ECC), 20GB SSD, 2TB/hó átvitel
  * **Linux 16**: 18 EUR/hó, 4 vCPU, 16GB RAM, 160GB SSD, 16TB/hó átvitel
  * SSID: RAID, 250 MB/s, 1000 IOPS, +1 EUR/hó gyorsítás
  * +1 EUR/hó 1Gb/s hálózat
  * 50% kedvezmény az első havi vagy éves számlából
  * HP ProLiant DL360 Gen10, UPS, dízel generátorok
* https://www.time4vps.com/storage-vps/ Litvánia (Vilnus), OpenVZ, 100Mb/s hálózat, IPv4 + /128 IPv6 (kérésre több)
  * **0.25TB**: 3 EUR/hó, 1 vCPU (Intel Xeon E5-2603 v4), 0.5GB RAM (DDR4-1866 ECC), 256GB HDD (RAID, 200 IOPS), 2TB/hó átvitel
  * **2TB**: 10 EUR/hó , 1 vCPU, 4GB RAM, 2TB HDD, 16TB/hó átvitel
  * +1 EUR/hó 1Gb/s hálózat
  * 50% kedvezmény az első havi vagy éves számlából
* https://my.nexusbytes.com/cart.php?gid=10
  * **Storage-0.5T**: 4 USD/hó, 512MB RAM, 2 vCPU (3.5GHz), 500GB HDD, 2500GB/hó átvitel, IPv4 + /64 IPv6
  * Németország, New York City, Miami, Los Angeles
* https://www.prometeus.net/site/terakvm.php
  * **TERAKVM-1000**: 12.5 EUR/hó +ÁFA (1 évre), KVM, 2 vCPU, 4GB RAM, 100GB SSD + 1TB HDD (RAIDZ ZFS), 10TB/hó adatforgalom, IPv4 + /64 IPv6
  * Olaszország, Hollandia
* https://www.netcup.eu/vserver/vstorage.php
  * **S 1000 G7**: 18 EUR/hó (19% ÁFA-val), 1 vCPU, 2GB DDR4 RAM (ECC), 1.5TB HDD (SAS, RAID 6), KVM, 99.9% SLA, 1Gb/s hálózat (200Mb/s átlagos teljesítmény, 15 perces csúszóablakban 80Mb/s), 1 IPv4 + /64 IPv6
  * adatközpont: Nürnberg, Németország
* https://clients.inceptionhosting.com/cart.php?gid=30 "USA storage KVM 1000" 1TB 4.24 EUR/hó
* https://www.euserv.com/en/dedicated-server/instant64-rootserver/v6/instant64-ar-hdd-v6.php dedi Ryzen 3700X 20TB 46 EUR/hó
* https://www.wishosting.com/order/config/index/VPS/?group_id=2&pricing_id=42
  * nem találni információkat a cégről
  * **KVM NAT Storage**: $5/hó (3 hó), 1 vCPU i7-3770, 1GB RAM, 1TB HDD RAID-5, 250Mb/s, korlátlan forgalom, NAT, Németország

#### Készlethiányos ajánlatok

* https://buyvm.net/kvm-dedicated-server-slices/
  * **SLICE 512**: $1.67/hó, 1 vCPU, 512MB RAM, 10GB SSD, korlátlan forgalom, IPv4
  * USA cég, elérhető adatközpontok: Las Vegas, New York, Miami, Luxembourg
  * https://buyvm.net/block-storage-slabs/ https://my.frantech.ca/cart.php?gid=46
    * +1TB HDD $5/hó, +10TB $50/hó
    * +10% biztonsági mentés

### Kiemelt olcsó, szabad szoftvert kiszolgáló cégek

* https://hosting55.hu/?nextcloud-tarhely
  * NextCloud
  * 2700 Ft/hó, 100 GB tárhely, korlátlan felhasználó
* https://maxer.hu/felho-tarhely.html
  * NextCloud
  * 5900 Ft/hó+ÁFA, 100 GB
  * ingyenes promóció? https://cloudtarhely.com/felhotarhely.html
* https://www.owncube.com/index_en.php
  * Megbízható múltra visszatekintő
  * Storage VPS kiterjesztett tárhellyel (500GB 15 EUR/hó, 20TB 80 EUR/hó)
  * Van hosted NextCloud, Onlyoffice, Collabora, Jitsi, Rocket.chat, BBB

### Privátszféra

* https://njal.la/
  * 15 EUR/hó, 1 vCPU, 1.5GB RAM, 15GB SSD tárhely, 1.5TB/hó adatforgalom
  * kriptovaluta elfogadott
  * PGP és XMPP ügyfélszolgálati kommunikáció
  * Svédország
* https://pay.privex.io/order/package/vmicro-se
  * **VMICRO-SE**: $0.99/hó, 2 vCPU, 256MB RAM, 5GB SSD tárhely, 100Mb/s, csak IPv6
  * **WEBBOX-SE-V1**: $5/hó, 4 vCPU, 1GB RAM, 20GB SSD tárhely, IPv4 + IPv6
  * kriptovaluta elfogadott: HIVE, HBD, EOS, Doge, Monero, LTC, BTC
  * email és Discord ügyfélszolgálati kommunikáció
  * Svédország
* https://cockbox.org/
  * $10/hó, 0.5 vCPU, 1GB DDR4 RAM, 30GB SSHD (SSD cached HDD), 10Gb/s "igazságosan megosztott" átvitel (a többi csomagnál ez 1TB/hó)
  * kriptovaluta elfogadott: Bitcoin
  * szerver: Románia
  * cég: Seychelle-szigetek
* https://monovm.com/linux-vps/
  * **Linux 512 MB**: 1 vCPU, 512MB RAM, 15GB SSD, 500GB/hó adatforgalom
  * VMware ESXi
  * https://monovm.com/buy-vps-with-bitcoin/
  * kriptovaluta elfogadott
  * cég: Litvánia
  * szerver: USA(San Jose, Chicago, New York), UK(Manchester), Netherlands(Amsterdam), Germany(Frankfurt), Canada(Montreal), France(Paris)

## Árösszehasonlító oldalak

* https://www.serverhunter.com/
* https://en.metadedi.net/
* https://getfastvps.com/
* https://www.comparevps.com/
* http://www.lowendstock.com/

## Pingback

Ha átnevezésre vagy áthelyezésre kerül ez a fájl, az összes közvetlen hivatkozást frissíteni kell:

* https://hup.hu/comment/2555753#comment-2555753
* https://hup.hu/comment/2589108#comment-2589108
