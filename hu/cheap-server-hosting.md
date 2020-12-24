# Legolcsóbb szerverszolgáltatások

## Javaslatok

Tipikusan tesztelési vagy egyszemélyes felhasználásra.

Az ötlet, hogyha egy informatikában kicsit jártasabb ismerősünk meglátja a magunk által üzemeltetett szabad szoftveres alternatívákra mutató linkjeinket akkor tudjunk kérésre neki is egy konkrét szolgáltatót és árat ajánlani, illetve egy kattintásos telepítési utasítást. Ezt akár egy kis szöveges bannerrel is megtehetjük minden oldalunk alján.

Az alapvetés, hogy normál felhasználásra KVM-es gépek legalább félig dedikált magokkal, SSD-vel, biztonsági mentéssel ajánlhatók. Minden más (OpenVZ, LXC, üresjáratból szétosztott CPU, HDD) főleg csak próbálkozásra vagy nagyon minimális és CDN útján gyorsítótárazott szolgáltatásokra javasolt amit egyszerre csak 1-2 felhasználó fog megnyitni.

Amennyiben kiszemeltünk egy ilyet és van erre lehetőség, érdemes olyan helyet keresni ahol vannak nagyobb, de még mindig jó ár-érték arányú csomagok és biztosított a próbahónap vagy rövid távú fizetős konstrukció is, hogyha kevésnek találjuk a teljesítményt, tudjunk bővíteni.

## Magyarok

Itt az lenne a koncepció, hogy a személyes adataink ne hagyják el az országot.

_TODO: Ideálisan utána kéne járni egyenként, hogy kinek hol vannak a szerverei._

### Legolcsóbb magyarok

* https://ugyfelkapu.hostingbazis.hu/cart.php?a=add&pid=212 301 + áfa (383, 1 év)
  * **LXC VPS Micro**, LXC, 1 vCPU (2.8GHz), 1GB RAM, 10GB HDD (SAS RAID10), korlátlan adatforgalom, 1Gb/s, IPv4 + IPv6 (elvileg magyar: SzerverPlex.hu Kft. Budapest, 1132 Victor Hugo utca 18-22)
* https://rackoonet.hu/openvz-7-vps/ 490 (alanyi adómentes)
  * **OVZ7-START (2020)**: OpenVZ 7, 1 vCPU (HP DL380, 2x Intel Xeon 6-core +HT, 3GHz), 512MB RAM, 5GB HDD (6x HP 10k SAS, HP HW RAID10 + FBWC), korlátlan adatforgalom, 200Mb/s, IPv4 (elvileg magyar: Victor Hugo 18-22)
* https://atw.hu/vps 445 + áfa (2 év)
  * **egyéni VPS konfigurátor**, KVM, 1 vCPU, 512MB RAM, 5GB SSD (DRBD mirror), 1Gb/s, IPv4 + IPv6 (elvileg magyar: Victor Hugo 11-15, 18-22)
* https://vps4you.hu/hu/ssdvps 600 (alanyi adómentes?)
  * **SSD VPS 512MB**, KVM, 1 vCPU (Dell C6100, Intel Xeon CPU X5650 @ 2.67GHz), 512MB RAM (DDR3 ECC), 5GB SSD (Intel PC RAID), ~30TB/hó adatforgalom (<100Mb/s), 1Gb/s (2*1Gb/s szerverenként), IPv4 + IPv6 (elvileg magyar: DENINET Kft 1188 Budapest, Bercsényi Miklós utca 79/b)
* https://xethost.hu/vps-berles/ 890 + áfa
  * **Linux Cole**, VMware ESXi?, 1 vCPU (2.0GHz, E5-2530 v4?), 512MB RAM, 10GB SSD, korlátlan adatforgalom, 100Mb/s, IPv4 + IPv6 (elvileg magyar: Victor Hugo 18-22)

### Normál árú magyarok

* http://szervernet.hu/vps 1000 + áfa
  * **Xencloud Small**, Xen, 1 vCPU, 1GB RAM, 20GB HDD, korlátlan adatforgalom, IPv4 (tesztelve magyar: Victor Hugo 18-22)
* https://www.mikrovps.net/hu/vps/lxc 1000 + áfa
  * **LXC-1G**, LXC, 1 vCPU (Xeon E5), 1GB RAM, 20GB SSD, 1-5TB adatforgalom, 10Gb/s, IPv4 + IPv6 (elvileg magyar, DoclerWeb 1101 Budapest, Expo tér 5-7?)
* https://www.mhosting.hu/vps/ssd-vps 1000 + áfa
  * **SSD VPS - 0.5**, KVM, 1 vCPU (Dell PowerEdge, 6-magos Xeon 3.3-4.0GHz), 512MB RAM (DDR3 ECC), 15GB SSD, korlátlan adatforgalom, 1Gb/s (5Gb/s BIX uplink, 500Mb/s nemzetközi), IPv4 (elvileg magyar: Victor Hugo 18-22)
* https://www.seedworld.hu/vps.html 1000 + áfa (1270)
  * **VPS Start**, 1 vCPU, 1GB RAM, 15GB HDD, korlátlan adatforgalom, 100Mb/s (talán magyar: szerverpark.eu Victor Hugo 11-15)
* https://clans.hu/vps-standard 1000 + ?
  * **VPS Standard S**: KVM, 2 vCPU (INTEL XEON E5-2450 MAX 2.30 GHZ), 2GB RAM (DDR3 1600MHz), 10GB SSD (NVMe RAID), korlátlan adatforgalom, 100/100Mb/s, IPv4 (elvileg magyar, de ismeretlen helyen)
* https://vgh.hu/linux_vps 1250 (alanyi adómentes)
  * **HDD 1024**, VMWare, 1 vCPU, 1GB RAM, 20GB HDD, korlátlan adatforgalom, IPv4
* https://szerverpark.eu/vps 1250 + áfa (1 év)
  * **VPS START**, 1 vCPU, 1GB RAM, 15GB HDD, korlátlan adatforgalom, 100Mb/s (elvileg magyar: Victor Hugo 11-15)
* http://www.profivps.hu/vps 1260 + áfa (1600)
  * **Magyar VPS minimál**, OpenVZ (kérésre teljes virtualizáció), 2 vCPU (1500MHz), 512MB RAM, 10GB HDD (SAS), korlátlan adatforgalom, IPv4 + IPv6 (elvileg magyar: DENINET Kft 1188 Budapest, Bercsényi Miklós utca 79/b)
* https://szerverplex.hu/virtualis-szerver-berles/ 1267 + áfa (1 év)
  * **KVM VPS Flexible HDD**: KVM, 1 vCPU (HP DL580 4x Intel E7 szériás 8-10 magos), 2GB RAM (DDR3 ECC), 20GB HDD (HP SAS 6G, 10K RPM, HW RAID10), 1Gb/s (garantált 20% belföld, 5% külföld, 10Gb/s szerverenként), IPv4 + IPv6 (elvileg magyar: Victor Hugo 18-22)
* https://jztkft.hu/vpshosting.php#level-1-0 1500 + ?
  * **Linux VPS Mini**, Xen, 1 vCPU (Intel Xeon X5675), 2GB RAM (DDR3L 1333MHz ECC), 20GB HDD (WD Gold Enterprise, Dell Raid10), korlátlan adatforgalom, 1Gb/s (10Gb/s szerverenként), IPv4 + IPv6 (elvileg magyar: Victor Hugo 18-22)
* https://rackforest.com/szolgaltatasok/vps/#linux-vps 1500 + áfa
  * **Linux VPS One**, KVM, 1 vCPU (Xeon E5), 1GB RAM, 20GB SSD, 10Gb/s (2Gb/s garantált), 30TB/hó adatforgalom (efölött 100Mb/s korlátlan), IPv4 + IPV6 kérésre (elvileg magyar: Dataneum Kozma utca 2, Victor Hugo 18-22, Dataplex Asztalos Sándor utca 13)

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

* https://clients.inceptionhosting.com/cart.php?gid=22 "OpenVZ UK OVZ256" 0.83 EUR/hó

Itt egy másik jegyzetünk ami arra koncentrált, hogy hol lehet hónapokig, évekig vagy akár korlátlanul teljesen ingyen szervert futtatni, de ezek tipikusan nem etikus szolgáltatók:

* https://gitlab.com/bkil/hardware/-/blob/master/doc/hu/free-cloud.md

### Nemzetközi példák normál felhasználásra

* https://www.arubacloud.hu/vps/virtualis-privat-szerver-ajanlat-tipusok.aspx 900 + áfa
  * **Cloud VPS Small**, VMWare, 1 vCPU, 1GB RAM, 20GB SSD, 2TB/hó adatforgalom, IPv4 + IPv6
* https://www.hetzner.com/sb pl. dedicated: core i7-2600 2x4TB HDD 16GB RAM 34 EUR/hó
* https://www.kimsufi.com/en/servers.xml KS-3 Atom 2c/4t 1.86GHz, 4GB RAM, 2TB HDD 8 EUR/hó+áfa
* https://clients.inceptionhosting.com/cart.php?gid=30 "USA storage KVM 1000" 1TB 4.24 EUR/hó
* https://www.euserv.com/en/dedicated-server/instant64-rootserver/v6/instant64-ar-hdd-v6.php dedi Ryzen 3700X 20TB 46 EUR/hó

### Kiemelt olcsó, szabad szoftvert kiszolgáló cégek

* https://www.owncube.com/index_en.php
  * Megbízható múltra visszatekintő
  * Storage VPS kiterjesztett tárhellyel (500GB 15 EUR/hó, 20TB 80 EUR/hó)
  * Van hosted NextCloud, Onlyoffice, Collabora, Jitsi, Rocket.chat, BBB

## Árösszehasonlító oldalak

* https://www.serverhunter.com/
* https://en.metadedi.net/
* https://getfastvps.com/
* http://www.lowendstock.com/

## Pingback

Ha átnevezésre vagy áthelyezésre kerül ez a fájl, az összes közvetlen hivatkozást frissíteni kell:

* https://hup.hu/comment/2555753#comment-2555753
