# Web hosting

Nem ingyenes szolgáltatások, de elég jó ár-érték arányt biztosítanak.

Célközönség:

* Tipikus otthoni felhasználók saját maguknak
* Család & barátok
* Aki a szabad közösséget szeretné szolgálni

Emiatt bruttó árak szerepelnek.

A felsoroltak tipikusan a legolcsóbb csomagok (vagy néha egy nagyobb aminek a jobb ár-érték aránya van) - tehát elérhető más csomag is a legtöbb szolgáltatónál. A legtöbb szolgáltatónál a legtöbb típusú termék kapható, ezek nem lesznek itt mindenhol keresztbe linkelve.

Ideális szem előtt tartani a szolgáltató etikusságát és a decentralizációt is (nemzeti vs. globális szolgáltatók).

Lásd még:

* Ingyen statikus tárhelyek: [free-static-web-hosting.md](../free-static-web-hosting.md)
* Ingyen dinamikus tárhelyek: [free-paas-dynamic-web-hosting.md](../free-paas-dynamic-web-hosting.md)
* Olcsó VPS: [cheap-server-hosting.md](../cheap-server-hosting.md)
* Az összes jogosult `.hu` regisztrátor (közvetlen értékesítő): https://www.domain.hu/regisztratorok/

## Fogalmak

* https://en.wikipedia.org/wiki/CloudLinux_OS
* https://www.cloudlinux.com/index.php/lve-manager
* https://www.cloudlinux.com/index.php/mysql-governor
* https://docs.cloudlinux.com/cloudlinux_os_components/#general-information-and-requirements-4

## Domain

* Az árak a hosszabbításra vonatkoznak - eleinte sok helyen adnak kedvezményt.
* Névszerver kiszolgálás (avagy fenntartás vagy "NS/DNS hosting") is benne foglalva: alapból 2 szerverrel
* .hu TLD szabályok
  * Később elvehetik tőlünk a nevünket ha nem ellenőrizzük - hiába volt eredetileg szabad
  * https://www.domain.hu/a-domain-nev-valasztas-formai-kovetelmenyei-magyar-karakterek/
    * Legalább 2, legfeljebb 63 karakter (punnycode-ban), viszont az összes 2 betűs .hu már foglalt
    * Betűkészlet [0-9a-záéíóöőúüű], kötőjel nem lehet az elején-végén vagy kötőjel után
  * https://www.domain.hu/specialis-nevek/
    * Második szintű közdomainek
    * Védett nevek: minden közdomain alatt védett nevek, csak közvetlenül a .hu alatt védett nevek
    * Településnevek
    * Országnevek
    * gov.hu
    * olimpia vonatkozásúak
  * https://www.domain.hu/miert-szukseges-korultekintes-a-nevvalasztasnal/
    * Védjegyek
      * Magyar: [Szellemi Tulajdon Nemzeti Hivatala](http://epub.hpo.hu/e-nyilvantartas/?lang=HU), [2](https://www.sztnh.gov.hu/hu/szakmai-oldalak/vedjegy/adatbazisok)
      * EU: [EUIPO](http://euipo.europa.eu/eSearch/)
      * [World Intellectual Property Organization](https://www3.wipo.int/branddb/en/)
      * [TMview nemzetközi védjegy adatbázis](https://www.tmdn.org/tmview/welcome.html?lang=hu)
    * Jogi személyek nevei
    * Megbotránkozást, gyűlölet-, vagy félelmet keltő nevek
    * Megtévesztő domain nevek
    * Személynevek: 2020-07-30 után megszűnt szabály
* .eu TLD szabályok
  * https://eurid.eu/en/register-a-eu-domain/rules-for-eu-domains/
    * EU állampolgár
  * https://eurid.eu/media/filer_public/b7/fb/b7fbb549-420f-4a8e-baaf-084d695e3a79/idna.pdf
    * csak a cirill, görög vagy latin karakterkészlet egyike használható és az egész névre ugyanaz
  * https://eurid.eu/en/register-a-eu-domain/rules-for-eu-domains/list-blocked-names/
    * tiltott nevek
  * EURid által fenntartott nevek
  * https://eurid.eu/d/374/2015_516_EN.pdf
    * bármely tagállam aki további fenntartási igényt nyújtott be

### 024reg domain és dinamikus tárhely

* https://www.024reg.com/tarhely/
* Székhely: 2724 Újlengyel, Petőfi Sándor utca 48. Euromarknet Kft.
  * regisztrátor
  * Infrastruktúra: (Weboldaluk IP címe alapján talán Rackhost Kft.)
* Árak
  * `.hu` 3500 Ft/év
  * `.eu` 5715 Ft/év
  * `.com` 5715 Ft/év
  * `.net` 5715 Ft/év
* Jár hozzá ingyen dinamikus tárhely vagy bővíthető
  * 2GB webtárhely + 1GB email tárhely
  * PHP
    * 128MB RAM
  * 1 MySQL adatbázis
  * 15 email fiók: POP3, SMTP
  * nincs HTTPS csak a fizetős tárhely csomagjaikkal
  * nincs telepítő

### Domdom domain és statikus tárhely

* https://www.domdom.hu/domain/domain-regisztracio
* Do Média Kft.
  * regisztrátor
* Árak
  * `.hu` 1512 Ft/év
    * _Ez csak időszakos kedvezmény?_
  * `.eu` 5068 Ft/év
  * `.com` 6979 Ft/év
  * `.net` 8884 Ft/év
* 3 névszerver
* Jár hozzá ingyen statikus tárhely
  * 50MB tárhely
    * FTPS
  * Korlátlan email átirányítás

### HonlapTárhely domain

* https://honlaptarhely.hu/domain
* Székhely: 8441 Márkó, Búzavirág u. 9. PlexNET Informatikai Kft.
  * nem regisztrátor, ismeretlen partner, honlapjának regisztrátora EV2 Internet Kft.
* Árak
  * `.hu` 1384 Ft/év
  * `.eu` 4433 Ft/év
  * `.com` 4433 Ft/év
  * `.net` 4433 Ft/év

### HostingBázis domain

* Promóciós partnerlink ha támogatnátok: https://ugyfelkapu.hostingbazis.hu/aff.php?aff=142
  * `Domain` menüpont
* Székhely: 4642 Tornyospálca, Mándoki út 40. HostingBazis Bt.
  * nem regisztrátor, ismeretlen partner, honlapjának regisztrátora Rackhost Zrt.
* Árak
  * `.hu` 2500 Ft/év
  * `.eu` 3216 Ft/év
  * `.com` 3331 Ft/év
  * `.net` 5401 Ft/év

### megacp domain

* Promóciós partnerlink ha támogatnátok: https://megacp.com/check.php?aid=urb40687
  * regisztrátor
* Árak
  * `.hu` 1651 Ft/év
  * `.eu` 2210 Ft/év
  * `.com` 3810 Ft/év
  * `.net` 5334 Ft/év
* Kedvezmény: tárhely csomagjaik mellé a `.hu`, `.eu`, `.com`, `.at`, `.ro` vagy `.co.uk` TLD alatti regisztráció ingyenes az első számlázási periódusra
* 3 névszerver és 3 MX bejegyzés

### njalla domain

* https://njal.la/
* kriptovaluta elfogadott
* PGP és XMPP kommunikáció
* névtelen bejegyzés is támogatott
* Árak
  * `.eu` 15 EUR/év
  * `.com` 15 EUR/év
  * `.net` 15 EUR/év
* További elérhető szolgáltatások: VPS, VPN

### BitLaunch VPS

* http://bitlaunch.io/
* névtelen fizetés is támogatott: cryptocurrency
* szerverek: saját, DigitalOcean, Vultr, Linode

### RackForest domain

* https://rackforest.com/szolgaltatasok/domain-regisztracio/
* 1132 Budapest, Victor Hugo u. 18-22.
  regisztrátor
* Árak
  * `.hu` 2286 Ft/év
  * `.eu` 3416 Ft/év
  * `.com` 4318 Ft/év
  * `.net` 6337 Ft/év

### WebHostIcon domain és statikus tárhely

* Promóciós partnerlink ha támogatnátok: https://webhosticon.hu/ugyfelkapu/aff.php?aff=461
  * `Domain` menüpont
* Székhely: 1081 Budapest Légszesz u. 4.
  * regisztrátora: 8790 Zalaszentgrót, Virág utca 9. 0-24 Domain Regisztrátor Kft. http://domainregisztratorkft.hu/ (csak viszonteladó)
* Árak
  * `.hu` 1715 Ft/év
  * `.eu` 3048 Ft/év
  * `.com` 4191 Ft/év
  * `.net` 6096 Ft/év
* Jár hozzá ingyen statikus tárhely vagy rendelhető dinamikus
  * 50MB tárhely
    * FTPS
    * SSI
    * .htaccess részlegesen
    * Egyedi hibaoldalak
  * 60GB/hó forgalom (a vezérlőpulton korlátlan), ÁSZF:
    * max. 1000 egyedi látogató/nap
    * max. 5000 oldalletöltés/nap
  * 10 email fiók: webmail, POP3, IMAP, SMTP, TLS
  * Napi webszerver naplók
  * Nincs HTTPS
  * Tiltott országok: JP, TH, KR, HK, TW, BR, UA

## Email

## Tárhely

* Tipikusan jár hozzá email is.
* FTP fiók
* Az adatbázisra kisebb korlát is vonatkozhatna mint a teljes tárhelyre
  * Korlátlan = tárhelybe számít bele, nincs külön korlát

### HostingBázis tárhely

* Promóciós partnerlink ha támogatnátok: https://ugyfelkapu.hostingbazis.hu/aff.php?aff=142
  * `Webtárhely` menüpont
  * 3000 Ft/év (alanyi adómentes)
* Székhely: 4642 Tornyospálca, Mándoki út 40. HostingBazis Bt.
* 1GB SSD tárhely
* Korlátlan forgalom
  * 1Gb/s
* Korlátlan email postafiók: webmail, POP3, IMAP
* Korlátlan használható domain
* HTTPS
* cron
* Telepítő

#### CPanel webtárhely small

* infrastruktúra: BIX adatközpontban (Talán ugyanott van mint a VPS szolgáltatásuk? Ha igen: SzerverPlex.hu Kft. Budapest, 1132 Victor Hugo utca 18-22)
* CPanel vezérlőpult
* CloudLinux
* PHP 5.6-8.0
* Korlátlan MariaDB 10.2 MySQL adatbázis
* Biztonsági mentés külső helyszínre

#### Webtárhely HU small

* infrastruktúra: magyar
* InterWorx vezérlőpult
* PHP 5.5-7.4
* Korlátlan MySQL 5.7
* Biztonsági mentés

### megacp tárhely

* Promóciós partnerlink ha támogatnátok: https://megacp.com/hosting.php?aid=urb40687&spt=1
* Székhely: 2310 Szigetszentmiklós, Brassó u. 4/A. 3 in 1 Hosting Bt.
* Infrastruktúra
  * magyar cPanel: Victor Hugo utcai (ATW Internet Kft. - "Dataland") vagy Kozma utcai (Invitech Megoldások Zrt. - "Invitel") szerverteremben: IPv4
  * magyar Interworx nem klaszter: budaörsi "Datanet" (Magyar Telekom Nyrt.) szerverteremben: IPv4 + IPv6
* **Induló tárhely csomag I, cPanel, magyar**: 4318 Ft/év (2 évente fizetve)
* 750MB SSD tárhely (RAID10)
* Korlátlan forgalom, 1Gb/s
* Korlátlan email postafiók: Horde és Roundcube webmail, POP3, IMAP, SMTP, továbbítók
* Korlátlan használható domain
* HTTPS: cPanel AutoSSL, aldomainekre is
* PHP 7.4, Perl, CGI
* Korlátlan MySQL 5.7 adatbázis
* cron
* Napi tárhely és adatbázis mentés
* Fantastico telepítő
* Kiszolgáló hardver: 2 * 8 magos CPU, 64GB RAM, 10Gb/s a webszerver és adatbázis szerver között, független terembe replikált adatbázis

### mhosting tárhely

* https://www.mhosting.hu/tarhely/webtarhely
  * **Start**: 1892 Ft/hó
* Székhely: 1132 Budapest Victor Hugo u. 18-22. Magyar Hosting Kft.
  * regisztrátor
* 250MB SSD tárhely
* Korlátlan adatforgalom
* PHP 5.3, 5.6, 7.1, 7.2, 7.3, 7.4, 8.0
  * memory_limit 256MB
  * host_max_size 50MB
  * upload_max_filesize 50MB
  * session_gc_maxlifetime 1440s
  * ImageMagick, cURL, Zend Optimizer (Guard Loader), ionCube Loader, APC PHP gyorsító, eAccelerator, Xcache, OPCache, memcached
* CloudLinux
  * 200% CPU
  * korlátlan vMEM
  * 512MB pMEM
  * 32 belépő folyamat (concurrent connections)
* 1 MariaDB 10.1.40 (MySQL) adatbázis
* 1 email fiók
  * webmail, IMAP, POP3, SMTP, catch-all, továbbítók
  * 150 db/óra küldhető
* cPanel vezérlőpult
  * Installatron telepítő
  * telepíthető webshop is
* Biztonsági mentés: napi, heti, havi
* 10 domain használható (vhost alias)
* cron
* Apache 2.4
  * mod_pagespeed
  * Perl 5, SSI
  * HTTPS: osztott, saját vagy Let's Encrypt

### RackForest tárhely

* https://rackforest.com/szolgaltatasok/tarhely/
  * **SSD ONE**: 4826 Ft/év
* Infrastruktúra: 1132 Budapest, Victor Hugo u. 18-22.
* 1GB SSD tárhely
  * korlátlan IOPS
  * Biztonsági mentés
* 1TB/hó forgalom
  * max. 1000 egyedi látogató/nap (javaslat)
* HTTPS
* ssh bejelentkezés
* PHP 4.4-7.4, Perl, Python 2.6.6
* cron
* Korlátlan MySQL 5.5 adatbázis
* Korlátlan email: webmail, továbbítók
  * max. 500 db/óra küldhető
* 5 domén használható
* Apache, rewrite
* CloudLinux
  * 100% CPU
  * 768MB RAM
  * 20 belépő folyamat
  * 80 folyamat összesen
* Softaculous telepítő

### VPS4You tárhely

* Promóciós partnerlink ha támogatnátok: https://vps4you.hu/r/vives
  * `Webtárhely` menüpont
  * **Web 250M** 249 Ft/év
  * _Web 1G 999 Ft/év_
* Infrastruktúra szolgáltató: DENINET Kft 1132 Budapest, Victor Hugo 18-22
* 250MB tárhely
  * max. 100000 fájl
  * tilos a "nagy számú" média fájl tárolása
* PHP 5.6, 7.2, 7.3, 7.4, 8.0 (igény szerint más verzió)
* MySQL
  * max. 15sec/lekérés
* SSL
* email cím
  * max. 100db/óra/felhasználó, max. 100db/óra/domain, nagy mennyiségű fogadás sem megengedett

### WebHostIcon tárhely

* Promóciós partnerlink ha támogatnátok: https://webhosticon.hu/ugyfelkapu/aff.php?aff=461
  * `Tárhely` menüpont
  * **Hangya tárhely**: 2131 Ft/év (3 évente fizetve), 200MB
  * _WebManó tárhely: 3387 Ft/év, 750MB_
  * _WebKobold: 5588 Ft/év, 1.5GB_
* Székhely: 1081 Budapest Légszesz u. 4.
* Infrastruktúra szolgáltató: ezit.hu
* 200MB tárhely
  * 1MB/s IO
  * 1024 IOPS
* 60GB/hó forgalom, ÁSZF:
  * max. 1000 egyedi látogató/nap
  * max. 5000 oldalletöltés/nap
* 5 domén használható
* korlátlan email fiók
  * webmail, POP3, IMAP, SMTP, továbbítók
  * max. 200 db/nap küldhető
* cron
* PHP 5.x-7.x
  * max_execution_time = 30
  * max_input_time = 60
  * memory_limit = 128M
  * post_max_size = 32M
  * upload_max_filesize = 32M
  * Ioncube loader, Zend Optimizer, ImageMagick, GD2
* 1 MySQL adatbázis
  * MAX_QUERIES_PER_HOUR = 30000
  * MAX_UPDATES_PER_HOUR = 20000
  * MAX_CONNECTIONS_PER_HOUR = 5000
  * MAX_USER_CONNECTIONS = 100
* CloudLinux
  * 50% CPU
  * 512MB VMEM (virtual), 256MB PMEM (physical)
  * 10 belépő folyamat
  * 20 folyamat összesen
  * max. 200MB RAM/folyamat
* Apache vagy OpenLiteSpeed
  * max. 200 kapcsolat/IP
  * max. 300 sec/folyamat
  * Van HTTPS https://webhosticon.hu/ugyfelkapu/index.php?rp=/knowledgebase/238
* Korlátozások
  * Tiltott függvények: apache_child_terminate, apache_setenv, define_syslog_variables, dl, escapeshellarg, escapeshellcmd, exec, highlight_file, ini_alter, ini_restore, mail, openlog, passthru, popen, pclose, posix_getpwnam, posix_getpwuid, posix_kill, posix_mkfifo, posix_setpgid, posix_setgid, posix_setsid, posix_setuid, proc_close, proc_get_status, proc_nice, proc_open, proc_terminate, shell_exec, show_source, symlink, syslog, system, virtual
  * Tiltott országok: JP, TH, KR, HK, TW, BR, UA
  * Webáruház nem engedélyezett: Hangya és WebManó csomagban
* Softaculous telepítő

### Wombathosting tárhely

* https://wombathosting.hu/hosting/
* **KisWombat csomag parkoló domaineknek**: 394 Ft/év
* 100MB tárhely
* korlátlan adatforgalom
* PHP
* MySQL
* 5 postafiók, 10 alias: webmail, IMAP, POP3, SMTP
* napi és havi biztonsági mentés
* cron
