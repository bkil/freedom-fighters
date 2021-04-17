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

## Domain

* Az árak a hosszabbításra vonatkoznak - eleinte sok helyen adnak kedvezményt.
* névszerver kiszolgálás (fenntartás vagy "NS/DNS hosting") is benne foglalva

### 024reg domain és dinamikus tárhely

* https://www.024reg.com/tarhely/
* Székhely: 2724 Újlengyel, Petőfi Sándor utca 48.
* Infrastruktúra: (Weboldaluk IP címe alapján talán Rackhost Kft.)
* Árak
  * `.hu` 3500 Ft/év
  * `.eu` 5715 Ft/év
  * `.com` 5715 Ft/év
  * `.net` 5715 Ft/év
* Jár hozzá ingyen dinamikus tárhely vagy bővíthető
  * 2GB webtárhely, + 1GB email tárhely
  * PHP
    * 128MB RAM
  * 1 MySQL adatbázis
  * 15 email fiók: POP3, SMTP
  * HTTPS

### HostingBázis domain

* Promóciós partnerlink ha támogatnátok: https://ugyfelkapu.hostingbazis.hu/aff.php?aff=142
  * `Domain` menüpont
* Székhely: 4642 Tornyospálca, Mándoki út 40.
* Árak
  * `.hu` 2500 Ft/év
  * `.eu` 3216 Ft/év
  * `.com` 3331 Ft/év
  * `.net` 5401 Ft/év

### RackForest domain

* https://rackforest.com/szolgaltatasok/domain-regisztracio/
* 1132 Budapest, Victor Hugo u. 18-22.
* Árak
  * `.hu` 2286 Ft/év
  * `.eu` 3416 Ft/év
  * `.com` 4318 Ft/év
  * `.net` 6337 Ft/év

### WebHostIcon domain és statikus tárhely

* Promóciós partnerlink ha támogatnátok: https://webhosticon.hu/ugyfelkapu/aff.php?aff=461
  * `Domain` menüpont
* Árak
  * `.hu` 1715 Ft/év
  * `.eu` 3048 Ft/év
  * `.com` 4191 Ft/év
  * `.net` 6096 Ft/év
* Jár hozzá ingyen statikus tárhely vagy rendelhető dinamikus
  * 50MB tárhely
    * FTP
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
* Székhely: 4642 Tornyospálca, Mándoki út 40.
* 1GB SSD tárhely
* Korlátlan forgalom
  * 1Gb/s
* Korlátlan email: webmail, POP3, IMAP
* Korlatlan domain használat
* HTTPS
* cron

#### CPanel webtárhely small

* infrastruktúra: BIX adatközpontban (talán ugyanott van mint a VPS szolgáltatásuk? SzerverPlex.hu Kft. Budapest, 1132 Victor Hugo utca 18-22)
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
* MySQL 5.5 korlátlan adatbázis
* Korlátlan email: webmail, továbbítók
  * max. 500 db/óra küldhető
* 5 domén használat
* Apache, rewrite
* CloudLinux
  * 100% CPU
  * 768MB RAM
  * 20 belépő folyamat
  * 80 folyamat összesen

### WebHostIcon tárhely

* Promóciós partnerlink ha támogatnátok: https://webhosticon.hu/ugyfelkapu/aff.php?aff=461
  * `Tárhely` menüpont
  * **Hangya tárhely**: 2131 Ft/év (3 évente fizetve), 200MB
  * _Manó tárhely: 3387 Ft/év, 750MB_
  * _WebKobold: 5588 Ft/év, 1.5GB_
* Székhely: 1081 Budapest Légszesz u. 4.
* Infrastruktúra szolgáltató: ezit.hu
* 200MB tárhely
  * 1MB/s IO
  * 1024 IOPS
* 60GB/hó forgalom, ÁSZF:
  * max. 1000 egyedi látogató/nap
  * max. 5000 oldalletöltés/nap
* 5 domén használat
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
* Korlátozások
  * Tiltott függvények: apache_child_terminate, apache_setenv, define_syslog_variables, dl, escapeshellarg, escapeshellcmd, exec, highlight_file, ini_alter, ini_restore, mail, openlog, passthru, popen, pclose, posix_getpwnam, posix_getpwuid, posix_kill, posix_mkfifo, posix_setpgid, posix_setgid, posix_setsid, posix_setuid, proc_close, proc_get_status, proc_nice, proc_open, proc_terminate, shell_exec, show_source, symlink, syslog, system, virtual
  * Tiltott országok: JP, TH, KR, HK, TW, BR, UA
  * Webáruház nem engedélyezett: Hangya és WebManó csomagban