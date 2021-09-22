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

### breadpunk.club

* https://breadpunk.club/
* tildeverse tag
* ssh, IRC (InspIRCd, weechat, irssi), NNTP, webtárhely, gopher, gemini, email
* monetizáció: LibrePay

### buzon.uy

* https://buzon.uy/
* Webmail ("mail"), Taiga ("procyectos"), Mattermost ("team"), PrivateBin ("paste"), Searx ("searx"), Prosody (Jabber/XMPP), IRC ("irc"), RSS ("rss"), EtherPad ("pad")
* adományok fogadása: PayPal

### disroot.org

* https://disroot.org/en/#services
* tagsághoz kötött: email, NextCloud, fórum (Discourse), XMPP Chat ("webchat"), projekt menedzsment tábla (Taiga, "board"), kódtároló (Gitea, "git")
* szabad: kereső (SearX, "search")
* ingyenes "covid19 kit": Etherpad ("pad"), Ethercalc ("calc"), pastebin (PrivateBin, "bin"), fájlmegosztás (Lufi, "upload"), szavazás (Framadate, "poll"), videokonferencia (Jitsi Meet, "calls"), hanghívás (Mumble, "mumble"), dokumentum kollaboráció (CryptPad, "cryptpad")
* korlátozva van az időegységen belül kiküldhető emailek száma

### envs.net

* https://envs.net/
* tildeverse tag
* szolgáltatások
  * linkrövidítő
  * nullpointer (parancssoros fájlfeltöltő)
  * getwtxt ("twtxt", mikroblogging)
  * gitea ("git")
  * hedgedoc ("hedgedoc", kollaboratív markdown szerkesztés)
  * "matrix" (Matrix Synapse, Element, Dimension, mjolnir)
  * pleroma ("pleroma")
  * privatebin ("pb", pastebin képeknek)
  * Searx ("searx")
  * tiny tiny RSS ("rss")
  * Modoboa ("mail", webmail, 250MB)
  * Mailman3 ("lists")
  * "bbj" (fórum)
  * drone CI ("drone")
  * IP címünkkel kapcsolatos információk ("ip")
  * webtárhely (statikus, SSI, jelszóvédelem, PHP, sh, perl, Python, lua, cgi-bin)
  * blog (ttbp, bashblog)
  * adatbázis (sqlite, kérésre mysql)
  * gopher (+proxy)
  * gemini
  * webirc
  * znc
  * DNS (DNS-over-TLS)
* ssh
  * 1GB tárhely
  * max. 200 egyidejű szál
  * mosh
  * systemctl/loginctl linger
  * finger
  * cron, at
* CryptPad ("pad")
  * cryptdrive ("drive")
  * rich text ("pad")
  * táblázatkezelő ("sheet")
  * markdown szerkesztő ("code")
  * prezentáció ("slide")
  * szavazás ("poll")
  * ütemezés ("kanban")
  * "whiteboard"
  * file drop ("file")
  * teendők ("todo")
  * névjegyek ("contacts")
* monetizáció: LibrePay
* infrastruktúra: https://git.envs.net/envs/ops

### Feneas.org

* http://feneas.org/
* jelenleg 12 EUR/év a tagdíj, de van amelyik szolgáltatásuk díjmentes
* WeDistribute (hírek, leírások), Fediverse.party (népszerűsítés)
* Searx (kereső), Matrix/Element (csevegés), Friendica (közösségi háló), Diaspora (közösségi háló), Etherpad (közös jegyzetelés), GitLab (kód), Nextcloud (biztonsági mentésnek vagy doksik, stb), Collabora (dokumentumszerkesztés), Discourse (fórum)
* infrastruktúra: https://git.feneas.org/feneas/infrastructure/ansible

### Framasoft

* https://degooglisons-internet.org/en/list

### libranet.de

* https://libranet.de/
* Friendica, XMPP, NextCloud ("nc")

### monocles.de

* https://monocles.de/more/
* Szolgáltatások: ocean Cloud (4GB NextCloud), confer (videó konerencia, NextCloud Spreed.ME), email (1GB, Rainloop és egy másik webmail), interact chat (XMPP, 1 hónap csevegéstörténettel), monocles Web search (searx), monocles translator (LibreTranslate - Argos Translate), monocles live (Invidious), monocles social (Mastodon)
* Alkalmazások: Android webböngésző, Android XMPP kliens
* monetizáció: levelezőboríték, banki átutalás, Transferwise, PayPal, IOTA (crypto), tagdíj (24 EUR/6 hó)

### nogafam.es

* https://www.nogafam.es/#servicios
* Szolgaltatások
  * Mastodon ("masto")
  * Friendica ("friends")
  * Pixelfed ("pixel")
  * PeerTube ("video")
  * Lemmy ("forum")
  * Funkwhale ("music")
  * Matrix Synapse ("matrix")
  * XMPP
  * email ("mail", RainLoop)
  * Jitsi Meet ("jitsi")
  * Mumble ("turn")
  * Nextcloud ("cloud")
  * Searx ("searx")
  * Plume ("plume", blog)
  * WriteFreely ("writeas")
  * Miniflux ("rss", RSS aggregátor)
  * Wallabag ("share")
  * [Porl](https://github.com/cydrobolt/polr) ("u", linkrövidítő)
* adományok fogadása: LibrePay, PayPal, bankszámla

### poddery.com

* https://poddery.com/
* Matrix, XMPP, Diaspora

### privacytools.io

* https://www.privacytools.io/services/
* Searx, Mastodon, Matrix Synapse, Discourse, Peertube, Write Freely, PrivateBin

### reisub

* https://reisub.nsupdate.info/reisub/servicios.txt
* Friendica ("friendicarg"), Activitypub relay ("relay"), Imagebin ("imagebin", képfeltöltés), Pastebin ("paste"), Mumble, "bbs", Tiny Tiny RSS ("rss") [PlanetLibre](https://github.com/selairi/planetlibre) (RSS olvasó, "planeta"), XMPP, linkrövidítő ("url"), BoZoN (fájlmegosztás, "filebin"), nginx/FTP, Wordpress weblapok, IRC (+bouncer), EasyPad ("pad"), "poll" (szavazás, egyéni), Gitweb ("git"), NextCloud, BitTorrent tracker ("torrent"), "smail" (biztonságos levelezés, egüeni), Flyspray (hibajegykezelő, "bugs"), "wiki", "phpftp" (ftp kliens), Gemini (+proxy), NTP szerver

### riseup.net

* https://riseup.net/
* email (1GB, IMAP, Roundcube), XMPP chat (lekapcsolás alatt!), VPN, levlista (sympa), wiki (crabgrass), etherpad, Up1 (kliens oldali titkosítású pastebin és imagebin)
* erősen korlátozva van az időegységen belül kiküldhető emailek száma

### snopyta.org

* https://snopyta.org/
* jelenleg szünetel a regisztráció
* Searx kereső ("search"), PrivateBin (pastebin, "bin"), HedgeDoc (markdown koeditálás, "pad"), Etherpad (WYSIWYG koeditálás), EtherCalc, XMPP, Mastodon ("social"), Jitsi Meet ("talk"), Framadate ("poll"), CyberChef ("toolbox"), Tiny Tiny RSS, Invidious, Nitter, Bibliogram
  * https://github.com/gchq/CyberChef
* Tor hidden service átjáró a legtöbb szolgáltatásukra

### teknik.io

* https://teknik.io/
* szakmai hírek (blog, podcast)
* Upload Files (kliens oldali titkosítású fájlmegosztás), Pastebin, Vault (mappák upload és paste részére), Url Shortener, Vault, Git (gitea), email (1GB, Rainloop), Mumble, IRC, személyes blogok

### trom.tf

* https://trom.tf/
* szabad szolgáltatások
  * Friendica ("social")
  * NextCloud ("files", 5GB tárhely)
  * PeerTube ("videos", korlátlan tárhely)
  * [facilmap](https://github.com/FacilMap/facilmap) ("maps", OpenStreetMap különféle rétegekkel)
  * CryptPad ("office", 300MB tárhely)
  * [snweb](https://github.com/standardnotes/web) ("notes", standardnotes)
  * Searx ("search")
  * Lufi ("send", fájlküldés, max. 3GB, max. 7 napra)
  * [RSS bridge](https://github.com/RSS-Bridge/rss-bridge) ("rss", RSS csatornát biztosít sokféle zárt weboldalhoz)
  * Wallabag2 ("bag", könyvjelző)
  * [diagramsnet](https://github.com/jgraph/drawio) ("diagrams")
  * OpenSondage ("poll")
  * EtherPad Mypads ("text")
  * [wemawema](https://framagit.org/luc/wemawema) ("meme", mém generátor)
  * [haste](https://github.com/toptal/haste-server) ("paste", pastebin)
  * [SPF Toolbox](https://github.com/charlesabarnes/SPFtoolbox) ("check")
  * [LibreSpeed SpeedTest](https://github.com/librespeed/speedtest) ("speed")
  * [LibreQR](https://code.antopie.org/miraty/libreqr/) ("qr")
* zárt szolgáltatások
  * [Nitter](https://github.com/zedeus/nitter) ("bird", Twitter proxy)
  * Invidious ("ytb", YouTube proxy)
  * Bibliogram ("insta", Instagram proxy)
  * Youtube music engine ("musik", Last.fm és YouTube proxy)
* infrastruktúra: YunoHost
* adományok: LibrePay

### undernet.uy

* https://undernet.uy/
* Webmail ("mail", Roundcube, IMAP), ownCloud ("cloud"), Airsonic ("air"), Mumble, Minetest ("mine"), Mastodon ("mastodon"), PeerTube ("tube"), [Honk](https://humungus.tedunangst.com/r/honk) ("muro", ActivityPub közösségi háló), Jabber ("jabber")
* adományok fogadása: PayPal

### Wakoma

* https://wakoma.co/nimble/
  * Video and audio calling and messaging: Jitsi, Synapse
  * High-speed file-sharing and synchronization: NextCloud
  * Voucher Sales (Share and sell access to your internet connection): RADIUSDesk, UniFi
  * Wireless network management: UniFi, OpenWISP
  * Social eLearning: build, run and take courses offline or online: Wakoma Learn
  * Accessing educational content: Kiwix
  * Building and hosting local websites and blogs: WordPress
  * Media streaming: Jellyfin, AVideo, Plex
  * Playing games and hosting game servers
  * Collaborative document and spreadsheet creation: Nextcloud, OnlyOffice
  * Downloading files (like Kiwix education ZIMs): Transmission
  * Social Networking and forums: Discourse, Wakoma Learn
  * Reading and organizing e-books: Calibre Web
  * Building photo and video galleries: Piwigo, Lychee
  * Conducting surveys, polls and questionnaires: Kobo/Enketo
  * Collecting ethical usage and traffic analytics: Matomo, AWStats
* https://github.com/Wakoma/Lokal/tree/main/config
  * https://wakoma.co/lokal/
  * Kiwix
  * Nextcloud
  * Jitsi
  * Wordpress
  * Jellyfin: Jellyfin is the volunteer-built media solution that puts you in control of your media. Stream media to any device.
  * UniFi Controller: Network Management Software that binds gateways, switches and wireless access points together with one graphical front end. (Not open source)
  * Transmission
  * Calibre Web
  * Matomo: Google Analytics alternative that protects your data and your customers’ privacy.
  * Collabora Office
  * Grafana: From dashboards to metrics, logs and traces. Choose what works best for you and your team.
  * Prometheus: Power your metrics and alerting with a leading open-source monitoring solution.
  * ResourceSpace: ResourceSpace open source Digital Asset Management software is the simple, fast, & free way to organise your digital assets.
  * AzuraCast: azuracast is a free and open-source self hosted web radio management suite.
  * Moodle
  * Kolibri: An education content library for easy access to Khan Academy and more.
  * TODO: Matrix Synapse, Matrix Element Web, OpenVPN

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
  * https://github.com/JeroenED/Ansible-Role-Friendica

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

## Szabad kézi üzemeltetés

Avagy így csinálják a többiek, akik nem akarnak GUI-ból kattintgatni vagy bevált recepteket konfigurációval összekötni, hanem megoldják saját implementációval:

* https://github.com/tildeclub/tilde.club/tree/master/docs

## Zárt szolgáltatáscsomag telepítők

* https://www.cloudron.io/store/index.html https://git.cloudron.io/cloudron a receptek szabadok
* https://docs.start9.com/misc-guides/available-services.html
  * Tor
  * kriptovalutákhoz: Bitcoin, Bitcoin Proxy, Lightning Network Daemon (LND), c-lightning, Ride the Lightning (RTL), Spark Wallet, BTCPayServer, Sphinx Chat
  * egyéb szolgáltatások: Bitwarden, Burn After Reading, Cups Messenger, File Browser, Mastodon, Embassy Pages
  * licenc: https://github.com/Start9Labs/embassy-os/blob/master/LICENSE.md
* https://softaculous.com/apps
* https://installatron.com/apps
* https://netenberg.com/fantastico-scripts.html
* https://www.plesk.com/extensions/category/web_app/

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
* biztonsági másolat szerverekről vagy kliensekről
* Optimalizáló web proxy

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
