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

* https://rackoonet.hu/openvz-7-vps/ 490 (alanyi adómentes)
* https://atw.hu/vps 549 + áfa
* https://vps4you.hu/hu/ssdvps 600 + áfa
* https://xethost.hu/vps-berles/ 890 + áfa
* https://www.arubacloud.hu/vps/virtualis-privat-szerver-ajanlat-tipusok.aspx 900 + áfa

### Normál árú magyarok

* https://www.mikrovps.net/hu/vps/lxc 1000 + áfa
* https://www.mhosting.hu/vps/ssd-vps 1000 + áfa
* https://www.seedworld.hu/vps.html 1000 + áfa (1270)
* https://clans.hu/vps-standard 1000 + ?
* https://vgh.hu/linux_vps 1250 (alanyi adómentes)
* https://szerverpark.eu/vps 1250 + áfa
* http://www.profivps.hu/vps 1260 + áfa (1600)
* https://szerverplex.hu/virtualis-szerver-berles/ 1490 + áfa
* https://jztkft.hu/vpshosting.php#level-1-1 1500 + ?
* https://rackforest.com/szolgaltatasok/vps/#linux-vps 1500 + áfa

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
