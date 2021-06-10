# Szolgáltatáscsomagok kialakítási módja

## Probléma

* Minél több alternatívára szeretnénk jó példával szolgálni, hogy megérje váltani a zárt szereplőkről.
* A saját üzemeltetés jelentős költségekkel jár infrastrukturális és emberi ráfordításokban. Ennek egy amortizációs módja ha olyan átfogó csomagokat nyújtunk, amiből 1-1 felhasználó várhatóan csak kevés elemet fog kihasználni.
* A meglévő hasonló FOSS szolgáltatók általában önkénteseket vesznek igénybe és még így is elég veszteségesek, jelentősen visszavágják idővel a palettát, ami egyre kevéssé teszi vonzóvá a platformot és csökkenti a szolgáltatók közti differenciálást.
* Hosszú távon jó lenne egy olyan egy-kattintásos keretrendszert (vezérlőpanelt avagy alkalmazás telepítőt) kifejleszteni mely üzemeltetéséhez minél kevesebb szaktudás szükséges.

## Meglévő szolgáltatók

### autistici.org

* https://www.autistici.org/services/
* email, blog (WordPress + BuddyPress), levlista, statikus web tárhely (a közelmúltig volt dinamikus is), csevegés (IRC, XMPP), konferencia (Jitsi, VLC live streaming), feladó rejtett email (anonymous remailer vagy nym)

### disroot.org

* https://disroot.org/en/#services
* NextCloud, XMPP Chat, Etherpad, Ethercalc, Pastebin, Online polls, Gitea

### Feneas.org

* http://feneas.org/
* jelenleg 12 EUR/év a tagdíj, de van amelyik szolgáltatásuk díjmentes
* WeDistribute (hírek, leírások), Fediverse.party (népszerűsítés)
* Searx (kereső), Matrix/Element (csevegés), Friendica (közösségi háló), Diaspora (közösségi háló), Etherpad (közös jegyzetelés), GitLab (kód), Nextcloud (biztonsági mentésnek vagy doksik, stb), Collabora (dokumentumszerkesztés), Discourse (fórum)

### Framasoft

* https://degooglisons-internet.org/en/list

### poddery.com

* https://poddery.com/
* Matrix, XMPP, Diaspora

### privacytools.io

* https://www.privacytools.io/services/
* Searx, Mastodon, Matrix Synapse, Discourse, Peertube, Write Freely, PrivateBin

### riseup.net

* https://riseup.net/
* email (1GB, IMAP, Roundcube), XMPP chat (lekapcsolás alatt!), VPN, levlista (sympa), wiki (crabgrass), etherpad, Up1 (kliens oldali titkosítású pastebin és imagebin)

### teknik.io

* https://teknik.io/
* szakmai hírek (blog, podcast)
* Upload Files (kliens oldali titkosítású fájlmegosztás), Pastebin, Vault (mappák upload és paste részére), Url Shortener, Vault, Git (gitea), email (1GB, Rainloop), Mumble, IRC, személyes blogok

## Szabad szolgáltatáscsomag telepítők

Érdemes összehasonlítani a kínálatukat, illetve érdekes volna kombinálni a palettákat valamilyen módon.

* https://freedombone.net/apps.html
* https://wiki.debian.org/FreedomBox/Manual#Apps
  * https://wiki.debian.org/FreedomBox/Features
* https://yunohost.org/en/apps?q=%2Fapps
* https://apps.sandstorm.io/
* https://github.com/arkOScloud/applications _elévült_
  * https://en.wikipedia.org/wiki/ArkOS
* https://homelabos.com/docs/#categories
  * https://gitlab.com/NickBusey/HomelabOS/
* Docker
  * https://dockstarter.com/
    * https://github.com/GhostWriters/DockSTARTer/
* Ansible
  * https://github.com/davestephens/ansible-nas
  * https://github.com/osm-fr/ansible-peertube
  * https://docs.joinpeertube.org/install-unofficial?id=ansible-on-debian

### sovereign

* https://github.com/sovereign/sovereign
* Ansible
  * email: Dovecot (Solr), Postfix, PostgreSQL, Rspamd, EncFS, Roundcube, Z-Push
  * Prosody XMPP
  * Selfoss RSS
  * ownCloud: tárhely, CalDAV, CardDAV
  * OpenVPN
  * ZNC IRC bouncer
  * monitoring: Monit, collectd
  * web hosting: Apache, ufw tűzfal, fail2ban
  * Tarsnap napi mentés
  * cgit, gitolite
  * Wallabag
  * ssh, mosh, htop

### streisand

* https://github.com/StreisandEffect/streisand
* Ansible
* nginx (sslh), OpenSSH (Tinyproxy), OpenConnect (ocserv), OpenVPN (dnsmasq, stunnel), Shadowsocks (libev, AEAD, V2ray-plugin), Tor bridge relay (Obfsproxy), WireGuard, ufw, unattended-upgrades, DNS-over-HTTPS
* Amazon EC2, Microsoft Azure, Digital Ocean, Google GCE, Linode, Rackspace

## Zárt szolgáltatáscsomag telepítők

* https://www.cloudron.io/store/index.html https://git.cloudron.io/cloudron a receptek szabadok
* https://docs.start9.com/misc-guides/available-services.html
  * Tor
  * kriptovalutákhoz: Bitcoin, Bitcoin Proxy, Lightning Network Daemon (LND), c-lightning, Ride the Lightning (RTL), Spark Wallet, BTCPayServer, Sphinx Chat
  * egyéb szolgáltatások: Bitwarden, Burn After Reading, Cups Messenger, File Browser, Mastodon, Embassy Pages
  * licenc: https://github.com/Start9Labs/embassy-os/blob/master/LICENSE.md

## Megcélzott szolgáltatások

### Kérdőív

* '''TODO''': Kérdőívvel kéne fókuszáltan megállapítani

### Teljes csomag

* '''TODO''': Külön kéne választani egy minimális részhalmazt ami olcsó VPS-en együtt futtatható
* felhasználói jogosultságkezelés és SSO: Keycloak, alternatívák:
  * openldap + dex
  * ory hydra + ory kratos
  * https://forge.tedomum.net/acides/hiboo/hiboo
* email (Dovecot?), webmail, levlista
* (statikus vagy PHP-) webtárhely, Wordpress (CMS weboldalakhoz)
* VPN
* Lemmy kérdéseknek és linkmegosztás
* közösségi háló: Friendica, (Pleroma, NextCloud Social)
* események: Mobilizon
* monitoring: Monitorix, NetData, YunoMonitor, Zabbix
* file sync: NextCloud (+contact), Syncthing, Seafile
* VCS: Gitea/Gogs
  * drone-ci -> ci ami remekül működik a gitea-val
* névjegyek sync: Radicale, Baikal
* dokumentum kollaboráció: OnlyOffice, (NextCloud, Collabora Online, CryptPad, Feng Office Community Edition, EtherPad, EtherCalc, TikiWiki Groupware, mediawiki)
  * egy gyakori kombináció: NextCloud + Collabora
* kérdőívek, szavazások: Framaforms
* prezentáció: Strut
* zero knowledge dokumentum kollaboráció: CryptPad
* zero knowledge nagy fájl feltöltő: Lufi
* (átmeneti) publikus képfeltöltés és kiszolgálás: Lutim
* pastebin: Zerobin
* könyvtár: Calibre-web
* időpont egyeztetés, szavaztatás: OpenSondage (Framadate)
* jelszókezelő: Bitwarden (?Keeweb)
* zenetár: Funkwhale
* videótár: PeerTube
* képtár: PixelFed
* csevegés: Synapse, Element (TODO: Construct)
  * XMPP (Prosody?)
* kereső: Searx
* apróhirdetések: PetitesAnnounces
* kanban tábla: Wekan
* családfa: Webtrees
* Személyi kapcsolati kezelő (Personal relationship manager, ~CRM): Monica
* FreeSwitch SIP szerver
  * TODO: Jitsi (NextCloud Talk?)
  * TODO: konferencia beszélgetések: Big Blue Button + Greenlight
  * TODO: https://github.com/edumeet/edumeet https://letsmeet.no/
  * STUN, TURN
* Moodle: elearning platform
* weblate: fordító platform
* TODO: PageKite/LocalTunnel
  * és/vagy dinamikus DNS kiszolgálás végfelhasználói IoT eszközök részére (vagy távmunka, biztonsági mentés, stb)
    * dinamikus DNS kiszolgálás csomagüzemeltetők részére
* OSM Tasking Manager
* biztonsági másolat

### Kisvállalati csomag

* Alkalmazottaknak
  * felhasználói jogosultságkezelés és SSO
  * email postafiók
  * szöveges azonnali üzenetküldő
  * levelező listák vagy valami más intraweb (pl. Friendica)
  * VPN
  * videokonferencia
  * időpont egyeztetés
  * naptáreseményre jelentkezés
  * kérdőívek
  * kanban tábla
  * valami tudásbázis (pl. wiki vagy git, lehetne szimulálni NextCloud alatt is kézi könyvtárakkal, de az kicsit fapados)
    * forráskód tároló, CI/CD
    * dokumentum archívum és fájlmegosztás (pl. NextCloud vagy git)
    * PeerTube az ügyféloldali reklámvideóknak és a belső továbbképzéshez
    * Moodle a belső továbbképzéshez
* Ügyfeleknek
  * statikus weblap
  * CMS
    * webshop
* Infrastruktúra
  * biztonsági másolat szerverekről vagy kliensekről
  * monitoring

## Külső hivatkozások

* https://www.autistici.org/links
* https://riseup.net/en/security/resources/radical-servers
