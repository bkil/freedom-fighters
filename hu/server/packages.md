# Szolgáltatáscsomagok kialakítási módja

## Probléma

* Minél több alternatívára szeretnénk jó példával szolgálni, hogy megérje váltani a zárt szereplőkről.
* A saját üzemeltetés jelentős költségekkel jár infrastrukturális és emberi ráfordításokban. Ennek egy amortizációs módja ha olyan átfogó csomagokat nyújtunk, amiből 1-1 felhasználó várhatóan csak kevés elemet fog kihasználni.
* A meglévő hasonló FOSS szolgáltatók általában önkénteseket vesznek igénybe és még így is elég veszteségesek, jelentősen visszavágják idővel a palettát, ami egyre kevéssé teszi vonzóvá a platformot és csökkenti a szolgáltatók közti differenciálást.
* Hosszú távon jó lenne egy olyan egy-kattintásos keretrendszert (vezérlőpanelt avagy alkalmazás telepítőt) kifejleszteni mely üzemeltetéséhez minél kevesebb szaktudás szükséges.

Lásd még:

* [palette-installer.md](palette-installer.md)
* [palette-inspiration.md](palette-inspiration.md)

## Kérdőív

* '''TODO''': Kérdőívvel kéne fókuszáltan megállapítani

## Teljes csomag

* '''TODO''': Külön kéne választani egy minimális részhalmazt ami olcsó VPS-en együtt futtatható
* felhasználói jogosultságkezelés és SSO: Keycloak, alternatívák:
  * openldap + dex
  * ory hydra + ory kratos
  * https://forge.tedomum.net/acides/hiboo/hiboo
* email postafiók (Dovecot?)
  * webmail
  * email továbbító alias címek, időkorlátos fogadó címek
  * felhasználók által létrehozott levlisták
* (statikus vagy PHP-) webtárhely, Wordpress (CMS weboldalakhoz, esetleg Drupal)
* VPN
* Lemmy kérdéseknek és linkmegosztás
* közösségi háló: Friendica, (Pleroma, NextCloud Social)
* események: Mobilizon
* monitoring: Monitorix, NetData, YunoMonitor, Zabbix
* file sync: NextCloud (+contact), Syncthing, Seafile
* VCS: Gitea/Gogs
  * drone-ci -> ci ami remekül működik a gitea-val
* névjegyek sync: Radicale, Baikal
* dokumentum kollaboráció:
  * OnlyOffice
  * NextCloud
  * Collabora Online
  * CryptPad
  * Feng Office Community Edition
  * EtherPad
  * EtherCalc
  * TikiWiki Groupware
  * mediawiki
  * https://github.com/hackmdio/codimd
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
* web proxy-k
  * optimalizáló
  * anonimizáló
  * Tor uplink
    * cache-elés, gyorsítás érdekében
    * ahol kliens oldalon tiltott a Tor
    * megosztó tartalmakhoz - akár a nem-Tor uplinkesek széleskörű családi szűrőket alkalmaznának a jogi aggályokat elkerülendő
* TODO: energiatakarékos mobil értesítéseke kiszolgálása
  * https://github.com/uniqush/uniqush-push
  * https://github.com/pmagaz/webpush-notification-server
  * https://unifiedpush.org/
    * https://bubu1.eu/openpush/
    * https://f-droid.org/en/2020/02/03/openpush-talk.html
    * https://unifiedpush.org/users/distributors/nextpush/
    * https://github.com/UP-NextPush/server-app
    * https://unifiedpush.org/users/distributors/ntfy/
    * https://gitlab.com/Nextcloud-Push/direct-push-proxy-v2

## Kisvállalati csomag

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

## Pingback

Ha átnevezésre vagy áthelyezésre kerül ez a fájl, az összes közvetlen hivatkozást frissíteni kell:

* https://hup.hu/comment/2697779#comment-2697779
