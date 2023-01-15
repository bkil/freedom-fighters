# Ingyenes dinamikus webtárhely

## Magyar reklámmentes

### aWh.hu

* https://www.awh.hu/hosting/webhosting
* 1GB SSD
* 100GB/ho adatforgalom
* 1 domain
* 0 postafiók
* 1 email átirányítás
* TLS ingyen
* PHP 7.4, 8.0, 8.1
* 1 MySQL adatbázis
* korlátlan aldomain
* HTTP/2
* .htaccess támogatott

### CWeb.hu

* https://cweb.hu/ingyen-tarhely
* 1GB SSD tárhely
* 3 adatbázis
* 3 domain, 3 aldomain (*.nvs.hu)
* 3 email fiók: POP3, IMAP, webmail
* PHP, Node.js, Python
* cPanel vezérlőpult
* alkalmazástelepítő: WordPress, Joomla, Opencart, Magento
* cron
* TLS ingyen
* CloudFlare
* CloudLinux
  * 10 MB/s I/O
  * 1024 IOPS
  * 25 belépő folyamat

### Nethely

* https://www.nethely.hu/ingyenes-tarhely
* Elhelyezkedés: BIX
* 256MB tárhely
* Nginx és Apache
* vagy 1 MySQL 5.7 vagy 1 PostgreSQL 11 adatbázis, korlátlan hellyel, privát phpMyAdmin
* PHP 5.6, 7.0, 7.1, 7.2, 7.3, 7.4, 8.0, CGI
* 1 email postafiók
  * 1 átirányítás
  * mérete korlátozható
  * webmail (RoundCube, Rainloop, Squirrelmail), SMTP, POP3, IMAP
  * max. 50 email/óra küldhető
* 9 aldomén is rendelkezésre áll, SSL nélkül, prefix `[0-9a-z]{3,}`
* Let's Encrypt SSL: csak saját domén esetén használható, varázslóval
* nincsenek időzített cron folyamatok
* Egy kérés időkorlátja: kb. 22 másodperc, bár max_execution_time=60
* regisztráció: nem fogadja el a plusz karaktert email címben, email megerősítés és Google ReCAPTCHA
* nincs biztonsági mentés
* egy tesztelt kiszolgáló: 200GB HDD RAID-1, 10GB RAM, AMD EPYC 7351P 16-Core @ 2.4GHz
* CMS alkalmazás telepítő: WebAppInstaller (WAI)
* csak a fizetős csomagban: cron időzített folyamatok, PHP gyorsító, SSD, részletes látogatottsági statisztika, HTTP/2, biztonsági mentés (Budapesten és Szegeden)

### NextNet.hu

* https://nextnet.hu/ingyen-ssd-tarhely/
* https://my.nextnet.hu/store/ingyen-tarhely
* 100MB tárhely
* korlátlan adatforgalom
* TLS ingyen
* SSD
* 2 email cím: IMAP, POP3, SMTP
* 1 domain + (1 domain vagy 2 aldomain)
* Apache2
* DirectAdmin vezérlőpult
* alkalmazástelepítő: WordPress, Joomla, Drupal, OpenCart

## Magyar reklámos

### ATW

* https://atw.hu/ingyenes-webtarhely
* Apache (+Nginx terheléselosztók)
* PHP
  * max. 20 küldött email/nap (`mail()`)
* MySQL
* email fiók: POP3, IMAP, SMTP, 5MB tárhely!
* 1 aldomén rendelkezésre áll
* cron

## Magyar megszűnt

### iHost

* https://robot.ihost.hu/cart.php?gid=2
* "Try" csomag
  * jelen pillanatban nem működik az ingyenes regisztrációs link
* 512MB tárhely (NVMe SSD)
* PHP 5.4-7.4
* CloudLinux
  * 200% CPU
  * 2GB fizikai RAM, 2GB virtualis RAM
  * 30 belépő folyamat
* korlátlan adatforgalom
* 3 adatbázis
* 3 hozzáadható domain, 3 aldomain
* ingyen SSL
* 3 email fiók (POP3, SMTP, IMAP)
* cPanel vezérlőpult
  * automata telepítő
* cron futtatás
* LiteSpeed Cache szerver oldali támogatás
  * HTTP/2
* biztonsági mentés: Jet backup

## Külföldi reklámmentes aldoménre is

### 000webhost

* https://www.000webhost.com/cheap-web-hosting
  * ennek az almárkája: https://www.hostinger.com/
* regisztráció:
  * hCaptcha és/vagy Google reCAPTCHA
  * csak a következő email címekről: aol.com (aim) mail.com live.com (outlook, hotmail, msn) icloud.com yandex.by yandex.kz gmx.com gmail.com facebook.com comcast.net usa.com inbox.lv
* 300MB tárhely
* 3GB/hó forgalom
* PHP
* MySQL
* 1 cronjob
* nincs email fiók

### 1Apps

* http://www.1apps.net/
* 1GB tárhely
* 100GB/hó forgalom
* ASP 3.0, MS Access adatbázis
* korlátlan domén, 1 aldomén
* Windows 2012 R2

### 1GB.ua

* https://free.1gb.ua/
* 1GB tárhely
* PHP
* 3 postafiók: POP3, SMTP

### 50Webs

* https://www.50webs.com/web-hosting/free/
* 500MB tárhely
* 5GB/hó forgalom
* Perl, Python, SSI
* nincs MySQL
* 10 domén, 100 aldomén
* 100 email postafiók, 10 alias

### alwaysData

* https://www.alwaysdata.com/en/
  * https://blog.alwaysdata.com/tag/free-offer/
  * https://help.alwaysdata.com/en/accounts/public-cloud-restrictions/
* székhely: Párizs
* 100MB tárhely
* Node.js, Python, PHP, Ruby
* SSL
* scheduled tasks
* MariaDB, PostgreSQL
* napi biztonsági mentés 30 napra visszamenőleg
* be kell lépni 4-12 havonta a webes felületre
  * https://help.alwaysdata.com/en/accounts/alerts-notifications/#lack-of-activity
* email, levelezőlista
* FTP, API

### AspOne

* https://www.aspone.cz/cz/Webhosting/Freehosting/
* tárhely 40MB
* korlátlan forgalom
* ASP.NET 4.0, MS Access, IIS 7, MS SQL 2008 R2

### Debian Developers

* https://wiki.debian.org/MemberBenefits
  * https://wiki.debian.org/ServicesHosting#Hosting_possibilities
  * https://wiki.debian.org/DebianDeveloper/JoinTheProject#Actually_joining_the_Project
  * https://www.rsync.net/debian.html
    * 500GB biztonsági másolat tárhely
* különböző szinteken kérvényezhetők különböző szolgáltatások (tárhely, VPS, dedikált gépek)
* debian.org subdomain
* libera.chat IRC cloak (álnév)
* ssh
  * https://db.debian.org/machines.cgi
* statikus webtárhely
  * ssh/scp public_html/
  * https://people.debian.org/~xxxxxx/
  * Apache

> Everybody who contributes to Debian is automatically a Debian Contributor.
> Benefits available to Debian members and contributors are listed below.

### Freehostia

* https://www.freehostia.com/free-cloud-hosting/
* 250MB tárhely
  * max. 2MB fájlméret
* PHP 4, 5, 7
  * Perl, Python, SSI
  * alkalmazástelepítő
* 10MB MySQL v5
* 6GB/hó forgalom
* 3 postafiók, RoundCube webmail
  * SMTP tiltva
* tucatnyi aldoménből választhatunk, 5 név használható egyszerre
  * saját domén
* Let's Encrypt SSL
* szerver: 24 mag, 64GB RAM, Apache, 2.5Gb/s, UPS & dízel aggregátor
  * Chicago, USA

### FreeHostingEU

* https://www.freehostingeu.com/
* 200MB tárhely
  * max. 15MB fájlméret
* 4GB/hó forgalom
* 1 domén, 5 domén
* ad 5 aldomént
* PHP 5, 7, CGI, Perl
* 1 * 30MB MySQL 5
* email fiók
* nincs cron

### Freeost

* http://freeost.com/premiumplan.php
* 500MB tárhely
* 500MB/hó forgalom
* max. 1000 új látogató/nap
* max. 2500 SQL kérés/óra
* saját domén vagy aldomén
* 3 cron feladat

### GearHost

* https://www.gearhost.com/documentation/add-a-credit-card-to-your-account
  * https://github.com/GearHost/Docs/blob/master/docs/how-does-hourly-pricing-work.md
  * https://github.com/GearHost/Docs/blob/master/docs/how-to-scale-your-cloudsite.md
* 1 vCPU, max. 5% CPU kihasználtság
* max. 1 worker
* 256MB RAM
* 1GB/hó hálózati forgalom
* 100MB tárhely
* hitelkártya nélkül fejlesztői csomag
* cron WebJob
  * https://github.com/GearHost/Docs/blob/master/docs/create-a-webjob.md
* email
  * max. 100 kimenő email/óra, max. 100MB/óra, afelett pufferel
  * max. 100 kimenő email/30 perc, afelett letilt és csak manuális terméktámogatási jegy útján oldják fel
  * max. 200 kapcsolódás/10 perc egyenként: IMAP, SMTP, POP3
  * https://github.com/GearHost/Docs/blob/master/docs/email-sending-policy-and-restrictions.md

### GoogieHost

* https://googiehost.com/freehosting.html
* 1GB tárhely
* 100GB/hó forgalom, afelett 100Mb/s
* PHP 5.3, 7.0.1
* 2 MySQL adatbázis
* 2 email postafiók
* Cloud Linux
* SSL
* cPanel vezérlőpult
  * Softaculous Auto-Installer telepítő
* LiteSpeed
  * CloudFlare CDN
* ssh
  * cron talán
    * https://client.googiehost.com/index.php/knowledgebase/86/How-to-setup-Cron-Job-.html

### HelioHost

* https://www.heliohost.org/
* PHP, ASP.NET, Java/JSP, Ruby on Rails, Django, Python, Perl
* MySQL, PostgreSQL, SQLite
  * korlátlan számú adatbázis
* email fiókok korlátlan számban
  * korlátlan levlista
* 1GB tárhely
* korlátlan forgalom
* TLS
* Softaculous telepítő
* 30 naponta cPanel belépés szükséges
* 10 másodperces időablakban max. 20% CPU, max. 20% RAM
* 1 cronjob, max. 2 futás/nap

### Host-ed

* https://www.host-ed.net/web-hosting.php
* 1GB HDD tárhely
  * max. 5MB fájlméret
  * max. 2MB feltölthető fájlméret
  * 25000 i-node
  * 256kB/s
  * minimum 1MB használata kötelező
* 10GB/hó forgalom (minimum 1MB/hó kötelező)
* 16% CPU
  * max. 5 párhuzamos web szerver lekérés
  * max. 10 párhuzamos folyamat
  * 100MB fizikai RAM
  * 32MB PHP memory_limit
* 1 * 10MB MySQL, 1 * 10MB PostgreSQL
  * 2% CPU
  * 256kB/s I/O
* PHP 5, ASP.NET, Perl, CGI, Ruby, SSI
* 1 crontab (max 1/óra)
* 3 saját domén, 1 aldomén
* email fiók
  * webmail, POP3, nincs IMAP, "korlátozott" SMTP
  * max 1 küldött email/óra
* SSL
* CloudLinux alapú szerver

### iXHosti

* https://ixhosti.com/
* magán csomagban 50GB tárhely
* üzleti csomagban korlátlan tárhely
* korlátlan forgalom
* max. 35 párhuzamos bejövő HTTP kapcsolat
* email
  * egy kimenő levélnek max. 500 címzettje lehet
* SSL
* telefonszám megadása kötelező
* régi nevén: 3Jelly

### Objectis

* http://www.objectis.org/
* Zope/Plone (Python) keretrendszert futtat
  * https://en.wikipedia.org/wiki/Zope

### PythonAnywhere

* https://eu.pythonanywhere.com/pricing/
* 512MB tárhely
* 1 aldomain, 1 webalkalmazás
* korlátozott kimenő hálózati forgalom és CPU használat
* Python 2.7, 3.6, 3.7, 3.8, 3.9, 3.10
  * számos telepített modul
* MySQL
* cron: naponta
* forrás feltöltése: git, mercurial, webes felület
* üzemeltetési háttér: Amazon EC2

### Webhosting-For-Free

* http://webhosting-for-free.com/free-web-hosting.html
* üzemeltető: axspace.com
* 100MB tárhely
* 1GB/hó forgalom
* 5 email fiók
* domén, aldomén

### Wikimedia Cloud Services

* 10-80 GB tárhely (bővíthető)
* 0.5-1 vCPU (bővíthető)
* 512MB-4GB RAM (bővíthető)
* választható: WMCS Cloud Services Introduction, VPS, IaaS, PaaS, DaaS, Toolforge, OpenStack, GridEngine, Kubernetes, K8s, infrastructure, Gerrit, Phabricator, bot, analytics, project, PHP7, Java, Mono, Python, Ruby, Golang, Node.js, Docker, screen, cron, tool, webservice, lighttpd, nginx
* https://wikitech.wikimedia.org/wiki/Help:Cloud_Services_Introduction
* https://wikitech.wikimedia.org/wiki/Wikitech:Cloud_Services_Terms_of_use#What_uses_of_Cloud_Services_do_we_like?
* https://wikitech.wikimedia.org/wiki/Help:Toolforge/Rules#Toolforge_rules

> to host your software tools for the Wikimedia movement, without charge.

## AttractSoft reseller

* a ResellerCluster üzemeltetője
* https://www.attractsoft.com/services/web-hosting-solutions/
* AttractSoft GmbH, Németország
* honlap segítő widget: livechat2.supportindeed.com
* ÁSZF visszaélés bejelentő email: abuse@supportindeed.com
* 5GB/hó forgalom
  * kötelező >0 B/12hó, különben inaktivitás miatt figyelmeztetés után törlik a fiókot
  * 12 havonta be kell lépni a vezérlőpultba
* 1GB tárhely
  * FTP
  * max. 15MB fájlméret (régen: 2MB)
  * max. 25k inode
  * webes fájlkezelő
* 1 email fiók
  * webmail, POP3, IMAP, SMTP
  * küldés: max. 31 küldött email/hó, max 5 címzett/levél, max. 2MB csatolmány
  * max 3000 fogadott email/hó
  * 1 alias
  * max. 50MB levélfiók tárhely
* kimenő TCP kapcsolatok tiltva
* Apache
  * SSL
  * tilos a hotlinking
* PHP 5.x, 7.4.2
  * GD library
  * nincs: SSI, cURL, ImageMagick, egyéni hibaoldalak, ssh, basic auth, naplófájlok
  * van: látogató statisztika, erőforrás kihasználtság
  * tiltott függvények: allow_url_fopen, fsockopen, pfsockpen, getrusage, get_current_user, set_time_limit, getmyuid, getmypid, dl, leak, listen, chown, chgrp, realpath, link. 
* CGI/Perl, PERL modulok
* 1 * 30MB MySQL 5.7 adatbázis
  * max. 30 párhuzamos kapcsolat
  * max. 12000 kérés/óra
* max. 4 weboldal
  * max. 3 aldomain biztosított (.c1.biz)
  * 1 saját domain
* Zacky alkalmazástelepítő, ingyenesen elérhető: Joomla, WordPress
* nincs crontab
* regisztrációhoz címadatokat kér

### ResellerCluster

* almárkái:
  * 125MB https://www.125mb.com/
  * 200MB Host http://200mbhost.com/
  * AcesHost http://aceshost.com/
  * AgilityHoster https://www.agilityhoster.com/
  * AlotSpace https://www.alotspace.com/
  * AtSpace https://www.atspace.com/web-hosting/free-hosting/free-hosting-all-features-table/
    * korlátlan forgalmat ígérnek (elírásnak tűnik)
  * AwardSpace https://www.awardspace.com/free-hosting/
  * BatCave https://www.batcave.net/
  * biz.nf https://biz.nf/web-hosting.php
  * CGI WebHost https://www.cgiwebhost.com/free-web-hosting.html
  * Free 150 http://free150.com/
  * Free Hosting No Ads: https://freehostingnoads.net/
  * Free-Host-Pro http://www.freehostpro.com/
  * Free-Host-Space: https://www.freehostspace.com/free-web-hosting.html
  * FreeSiteHosting: http://freesitehosting.com/
  * FreeWebPageHost: http://freewebpagehost.net/
  * GAT Free Host http://gatfreehost.runhosting.com/
  * iBestHosting http://ibesthosting.com/
  * iwebzhost https://iwebzhost.net/free-web-hosting.html
  * RedWebHost: https://www.redwebhost.com/free-web-hosting.html
  * RoyalWebHosting https://royalwebhosting.net/free-web-hosting.html
  * RunHosting
    * https://go.runhosting.com/index.html
    * https://go.runhosting.com/free-web-hosting.html
  * Tarhely.ml http://tarhely.ml/free-web-hosting.html
  * TekCities https://www.tekcities.com/
  * WebFreeHosting: https://webfreehosting.net/
  * ZettaHost
    * https://zettahost.com/free-website-hosting/
    * ZETTA HOSTING SOLUTIONS ltd. - ResellerCluster tulajdonosa?

## iFastNet reseller

* külföldi reklámmentes
* US
* whitelabel szolgáltató (Byet?) számos almárkával, üzemeltetője: ifastnet.com, regisztráció: securesignup.net
* https://github.com/InfinityFreeHosting/mofh-client
* PHP 5
* korlátlan MySQL adatbázis
* max. 10MB fájlméret
* ad aldomént
* Apache
* email fiók
* cron
* az oldalaink első megnyitásához JavaScript szükséges amivel injektál egy sütit a további lekérésekhez
  * https://forum.infinityfree.net/t/ensuring-only-web-browsers-can-access-your-website/49353
* kimenő hálózati forgalom engedélyezett bizonyos portokon (pl. HTTP, HTTPS, SMTP, FTP)
  * https://forum.infinityfree.net/t/can-i-use-sockets/49348

### 1-WS

* http://1-ws.com/
* korlátlan tárhely
* korlátlan forgalom
* SSL

### 5hark.net

* http://5hark.net/free-web-hosting.html
* http://v90.us/free-web-hosting.html
* 10GB tárhely
* 100GB/hó forgalom
* 10 MySQL
* 10 domén, 10 aldomén

### BooomHost

* http://booomhost.com/about-free-hosting.php
* üzemeltetője: MyOwnFreeHost, MX és hostname: ByetCluster.com, terméktámogatás: SecureSignup.net, iFastNet.com, byet.net
* 10GB tárhely
  * max. 10MB fájlméret
  * max. 30k inode
* 100GB/hó forgalom
  * max. 50k betöltés/nap
* 10 aldomén
  * xxxx.booomhost.com
  * booomhost.com powertechpoint.com suprahost.cu.cc 22web.org 10001mb.com 2kool4u.net 66ghz.com a0001.net fast-page.org html-5.me iblogger.org is-best.net is-great.net is-great.org likesyou.org loveslife.biz my-board.org my-style.in mydiscussion.net nichesite.org social-networking.me synergize.co talk4fun.net totalh.net web1337.net
* PHP 7.4.8
* cPanel vezérlőpult
  * Softaculous Apps Installer telepítő
  * nginx (Apache .htaccess értelmezés)
* TLS tanúsítvány beállítható
  * elsősorban csak fizetős
  * a Let's Encrypt .well-known HTTP kihívása nem működik mivel JavaScript nélkül nem elérhető
  * CNAME beállítható, így TXT proxy útján körüljárható Let's Encrypt is
* 10 MySQL korlátlan adatbázis
* cronjob
  * 5 másodpercen belül be kell fejeződnie vagy eltávolítják
  * akár 2 percenkénti gyakorisággal
  * akár több feladat
  * csak egy saját URI-t (scriptet) tud meghívni
* email: csak fizetős csomagban
* reklámbanner képet helyez el a HTML fájl végére

### Byet

* https://byet.host/free-hosting
* 1GB tárhely
* 50GB/hó forgalom

### Cart Webhosting

* http://www.cartwebhosting.com/freehosting.php
* 300MB tárhely
* 5GB/hó forgalom
* 1 domén, 5 aldomén
* 1 MySQL adatbázis

### Cloudy.eu.org

* http://cloudy.eu.org/about-free-hosting.php
* 1GB tárhely
  * max. 10MB fájlméret
* 10GB/hó forgalom
* 3 * MySQL korlátlan adatbázis
* 3 domén, 3 aldomén

### Crosshost

* http://crosshost.0lx.net/freehosting.php
* regisztráció: securesignup.net
* 250MB tárhely
* 6GB/hó forgalom
* 5 aldomén rendelkezésre áll
* saját domén is használható

### FreeCloudHost

* https://freecloudhost.org/
* Ez is szerepel a FAQ-ban: Cloudy.eu.org
* 1GB tárhely
  * 10MB fájlméret korlát
* 10GB/hó forgalom
* PHP
  * 24MB PHP memory_limit
* 1 MySQL adatbázis
* SSL
* LiteSpeed Enterprise quic.cloud CDN
* elvárás a fórumban való aktív részvétel
* nincs cron ("cannot run stand-alone, unattended server-side processes")

### dc7.us

* http://dc7.us/free-web-hosting.html
* 10GB tárhely
* 100GB/hó forgalom

### FnHost

* https://www.fnhost.org/
* "Sponsored by iFastNet", oda irányít a prémium regisztráció is
* korlátlan tárhely
* korlátlan forgalom
* 100 * MySQL 5.6 adatbázis
* PHP 5.4, 5.5, 5.6, 7.0
* Apache 2.4
* aldomén, korlátlan domén
* SSL
* 10 email fiók

### Free-Hoster

* http://free-hoster.net/free-hosting.php
* 10GB tárhely
* 100GB/hó forgalom
* 10 * MySQL korlátlan adatbázis
* 10 domén, 10 aldomén

### GetWeb.Cf

* http://getweb.cf/free-hosting.php
* 10GB tárhely
* 100GB/hó forgalom

### Host Free

* http://www.hostfree.pw/
* Ide átirányít: http://www.vhostfull.com/

### InfinityFree

* https://infinityfree.net/
* 5GB tárhely
* korlátlan forgalom
* PHP 7.4
* 400 MySQL 5.7 adatbázis
* TLS
* reklámmentes
* hozott domain vagy 25 aldomain valamelyike (pl. epizy.com  freecluster.eu infinityfreeapp.com)
* alkalmazástelepítő: Softaculous
* legfeljebb 3 fiók regisztrálható felhasználónként

### J77.us

* http://j77.us/free-web-hosting.html
* 7777MB tárhely
  * max. 10MB fájlméret
* 77777MB/hó forgalom
* 7 MySQL korlátlan adatbázis

### ProFreeHost.com

* https://profreehost.com/
* korlátlan tárhely
* korlátlan forgalom
* PHP
* 10 MySQL adatbázis
* honlapépítő
* email fiók: webmail, átirányítás
* subdomain: ezyro.com
* max. 10 domain, max. 10 aldomain
* max. 10 MB fájlméret
* SSL

### UHostAll

* http://www.uhostall.com/free-hosting.php
* regisztráció: vastserve.com
* korlátlan tárhely és forgalom
* SSL
* aldomén
* email postafiók, webmail
* MySQL
* cron

### U Host Full

* http://www.uhostfull.com/free-hosting.php
* regisztráció: ihostfull.com
* korlátlan tárhely
* korlátlan forgalom
* PHP
* MySQL
* SSL
* email fiók
* aldomén
* cronjob
* < 70% CPU

## Külföldi reklámmentes teljes doménre

### Flaunt7

* https://flaunt7.com/free-hosting/
* 10GB NVMe SSD tárhely
* korlátlan hálózati forgalom
  * max. 100 egyedi látogatói látogatás/nap
* DirectAdmin vezérlőpult
  * Softaculous App Installer telepítő
* ingyen Let's Encrypt TLS tanúsítvány
* CloudLinux
  * LiteSpeed web szerver
  * SSH
* székhely: Hollandia

### Freedomaini

* https://freedomaini.com/cart.php?a=add&pid=2
* 25GB tárhely
* nincs aldomén

### FreeHosting.com

* https://www.freehosting.com/free-hosting.html
* 10GB tárhely
* korlátlan forgalom
* PHP
  * 256MB memory_limit
  * nincs `mail()`,  és `sendmail` csak fizetős csomagban
  * 1 MySQL adatbázis
* Linux, Apache
  * .htaccess
* nincs aldomén
* hozott vagy új domainhez
* felhasználók blokkolva:  Brazília, Kuba, Irán, Szudán, Szíria, Vietnám.
* cPanel vezérlőpult
  * alkalmazástelepítő
* 1 webmail, IMAP, POP3, SMTP email
* nincs TLS
* reklámmentes
* székhely: Csehország

### HostPoco

* https://www.hostpoco.com/free-hosting.php
* 200MB tárhely
* 200MB/hó forgalom
* PHP
* 1 MySQL adatbázis
* nem biztosít aldomaint, de saját domain és 2 aldomain beköthető
* 2 FTP fiók
* 2 email fiók
* ingyen automatikus TLS
* cPanel vezérlőpult
* Softaculous alkalmazás telepítő
* regisztráció 24 órás manuális jóváhagyás után, elvárnak 10 napon belül egy publikus értékelést

### Nexus Bytes

* https://my.nexusbytes.com/cart.php?gid=1
* régi nevén: ServedEz
* korlátlan tárhely
  * 10MB/s I/O
  * 150000 i-node
* korlátlan forgalom
* nincs aldomén (csak 1 saját domén használatával)
* 3 * MySQL adatbázis
* 3 email fiók
* SSL
* PHP, Node.js, Python
* 25% CPU
  * 512MB RAM
  * 40 párhuzamos folyamat

## Külföldi reklámos

### 100Webspace

* https://www.100webspace.com/web-hosting/free-plan/
* 100MB tárhely
* 3GB/hó forgalom
* PHP 4, 5, 7, Perl, Python
* 5MB MySQL 5
* 1 domén (lehet, hogy subdomaint nem ad)
* 3 email fiók
* SSL
* telefonszám és egyéb adatok megadása kötelező

### FreeWebHostingArea

* https://www.freewebhostingarea.com/
  * https://freewha.com/
* 1500MB tárhely
  * max. 12MB fájlméret
* korlátlan forgalom
  * 1-3 havonta kötelező látogatót hozni
  * nagy tárhely foglaltság (>100MB) esetén legyen legalább naponta 1 látogató
* Apache 2.4 mod_rewrite, .htaccess
* PHP 5.6, 7.1, 7.2, 7.3
* MariaDB 10.4
* SSI
* `mail()` függvény alapból tiltott, de forgalmas, minőségi oldalak kérhetik a felkapcsolását

### Miarroba

* https://hosting.miarroba.com/features.php
* 500MB tárhely
  * Bizonyos tartalmakra akár 5GB tárhelyet is biztosítanak
* korlátlan forgalom
* PHP 5
* MySQL

### SimGames

* https://simgames.net/free-hosting/
* Kizárólag angol nyelvű, játékokkal és számítástechnikával ("gaming and technology") kapcsolatos weboldalak részére
* korlátlan tárhely, forgalom
* PHP CGI, Perl 5.8, SSI
* MySQL adatbázis
* korlátlan levelezés

### Somee

* https://somee.com/default.aspx
* 150MB tárhely
* 5GB/hó forgalom
* ASP.Net 2.0-4.8, ASP.Net Core 3.1
* 30MB MSSQL 2014, 2016, 2019
* Windows 2016

## Külföldi domén regisztrációhoz kötött

A következőknél a tárhelyért nem számítanak fel külön díjat, viszont ehhez náluk kell a doménnevet fenntartani.

### Pipni

* https://pipni.cz/?akce=jazyk&jazyk=EN
* 10GB tárhely
* 1TB/hó forgalom
* PHP, JSP, ASP
* adatbázis
* email fiók

## Összehasonlítások

Százával akadnak még külföldi alternatívák:

* https://www.100-best-free-webspace.com/webspace_01.php
* https://www.absolutely-free-hosting.com/free_hosts_01.php
* http://www.fhdir.com/
* https://freehosting1.net/hosting.aspx
* https://freehostsdir.com/
* http://www.free-webhosts.com/
* https://www.free-webspace.org/webspace_01.php
* https://hu.hostadvice.com/hosting-services/free-hosting/
* https://hostingfunda.com/free-hosting/
* https://www.hostsearch.com/free-web-hosting
* https://www.thefreecountry.com/webhosting/freewebhosts.shtml
* https://www.thefreesite.com/Free_Web_Space/
* https://github.com/publicsuffix/list

### Elévült

Megszűntnek látszik az alapján, hogy nagyon régen nem volt frissítve, nem működik a regisztráció vagy az ingyenes ajánlat már lejárt és csak fizetős elérhető:

* https://angelfire.lycos.com/hosting
* https://www.brinkster.com/
* https://buttobi.net/?n=service&l=en Regisztráció nem működik: surgesecure.net
* http://www.communityarchitect.com/
  * http://www.20m.com/
  * http://www.50megs.com/
  * http://www.biz.ly/
  * http://www.biz.tc/
* https://www.hostmedia.co.uk/
* https://www.netfirms.com/
* https://vimlyhost.net/
* https://x10hosting.com/ "a regisztráció átmenetileg szünetel"

#### 1freehosting

* https://www.1freehosting.com/
* regisztrációs link nem működik!
* 10GB tárhely
* 100GB/hó forgalom (kötelező: >0 B/hó)
* PHP5
* korlátlan domének, 5 aldomén
* 5 email fiók
* 5 * MySQL 5 adatbázis
* cron
* Apache

### Megszűnt

A domén vagy már szabad, vagy árulják, vagy reklámokat és ártó kódokat szolgálnak ki róla.

* http://www.000a.biz/
* http://www.5freehosting.com/
* http://www.5gbfree.com/
* http://888webhost.com/
* http://www.99on.com/
* http://www.bravenet.com/
* http://codenamecodi.ml/
* http://d33r.com/
* http://dwswebhosting.cf/
* http://fa5t.us/
* http://free-4u.eu/
* http://freehostinghero.com/
* http://www.freehostingking.com/
* http://www.freesite.org/
* http://www.freewebsitehosting.com/
* http://gdk.mx/
* http://globalwebbrands.com/
* http://www.hostcare.ml/
* http://i60.us/
* http://info8-hosting.info/ deceptive oldal, pedig iFastnet
* http://www.jabry.net/
* http://www.mzzhost.com/
* http://www.orgfree.com/
* http://www.sitepalace.com/
* http://www.vlexofree.com/
* http://www.webng.com/
* http://www.webspawner.com/
* http://wehostyou360.ml/
* http://xhosting.ml/

#### Mipropia

* https://mipropia.com/free-hosting/php/
* szolgáltató: iFastNet
* 3GB tárhely
  * max fájlméret 10MB
* 50GB/hó forgalom
* PHP 5.4, 5.5, 5.6, 7.0
* 4 * MySQL korlátlan méretű
* SSL
* 4 domén, 4 aldomén
* 158MB RAM

#### P8

* http://p8.hu/ (404)
* 100MB tárhely
* PHP
* MySQL
* 1 aldomén rendelkezésre áll
* nincsenek időzített cron folyamatok
