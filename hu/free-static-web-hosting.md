# Ingyenes statikus webtárhely

Egyes szoftver projekt tárolóknak is része a statikus webkiszolgálás és a CI/CD amivel honlapgenerálás is megvalósítható:

* [service/vcs-code-hosting.md](service/vcs-code-hosting.md)

## Keretrendszerek

* https://github.com/GetPublii/Publii
* https://en.wikipedia.org/wiki/Category:Static_website_generators
* https://en.wikipedia.org/wiki/Category:Free_static_website_generators
* https://en.wikipedia.org/wiki/Web_template_system#Static_site_generators
* https://en.wikipedia.org/wiki/Static_web_page
* https://staticadventures.netlib.re/blog/entering-the-static-web/
* https://feather.wiki/

## Magyar tárhely

Támogat tetszőleges HTML dokumentumok, benne CSS és JavaScript közzétételét.
Teljes HTML testreszabást ad.
Tipikusan FTP klienssel is feltölthető.
A kiszolgált oldal legfeljebb reklámbeszúrásban térhet el.

### IngyenWeb

* http://www.ingyenweb.hu/
* 200MB tárhely
* FTP és weboldalon feltöltés
* reklámot helyez el az oldal tetején
* nincs TLS
* aldomain: *.ingyenweb.hu
* nincs CORS

## Magyar honlapépítő

FTP hozzáférést és teljes HTML testreszabást nem ad.

### 5mp.eu

* https://www.5mp.eu/
* tulajdonos: Gáspár György EV
* infrastruktúra: Revo Systems Kft.
* 10MB tárhely
* reklámot helyez el
* nincs fájlfeltöltés
* aldomain: *.5mp.eu
* van TLS
* nincs CORS

### eOldal.hu

* https://www.eoldal.hu/
* 200MB tárhely
* tulajdonos: Central Médiacsoport Zrt.
* infrastruktúra: Websitemaster a.s. a NETHOST s.r.o., Csehország
* legalább 3 havonta be kell lépni az adminisztrációs felületre
* van TLS
* aldomain: *.eoldal.hu
* nincs CORS sem az oldalon, sem RSS-en

### ewk.hu

* https://ewk.hu/
* tulajdonos: Vilmányi Gergő EV, Vilmányi Xénia EV
* infrastruktúra: NLG-System Bt.
* 50MB tárhely
* nincs fájlfeltöltés
* reklámot helyeznek el
* van TLS
* aldomain: *.ewk.hu
* nincs CORS

### HuPont.hu

* https://www.hupont.hu/
* tárhely: korlátlan szövegeknek és képeknek
* reklámot helyeznek el
* tulajdonos: Mass Presence Kft.
* infrastruktúra: INTEGRITY Kft. (1132 Budapest, Victor Hugo u. 18-22.)
* nincs fájlfeltöltés
* nincs iframe beágyazás (csak YouTube)
* korlátozott HTML szerkeszthetőség
* nincs TLS
* aldomain: *.hupont.hu
* nincs CORS

### ini.hu

* http://ini.hu/
* 30MB tárhely
* 10 email cím
* üzemeltető: Deltha Rendszerház Kft.
* regisztráció csak papíron, levélben vagy faxolva beküldve, évente meg kell újítani!
* reklámokat helyez el
* nincs TLS
* nincs CORS

### Lapunk.hu

* https://lapunk.hu/
* korlátlan számú oldal
* kiegészítők: blog, hírek, cikkek, webshop, képgaléria, fórum, email kapcsolati űrlap, vendégkönyv, szavazás, látogatói statisztikák
* nincs TLS
* aldomain: *.honlapepito.hu *.qwqw.hu *.lapunk.hu
* nincs CORS

### NanoWeb.hu

* https://nanoweb.hu/
* 20MB tárhely
* korlátlan adatforgalom
* 1 honlap, max. 8 oldal (menüpont)
* max. 50 kép
* max. 15 fájl (képen kívül)
* kiegészítők: kapcsolati űrlap, vendégkönyv
* 1 widget: óra, eseménynaptár, névnap emlékeztető, szavazás, linkdoboz, szövegdoboz, megosztó gombok
* hirdetést jelenít meg
* saját hirdetés nem helyezhető el
* 1 aldomain: *.nanoweb.hu
* nincs CORS

## Magyar blog

A tárhely általában korlátlan.
A közzétehető dokumentumok köre megszorított.
A legkorlátozottabbakban szinte csak alapvető formázással szöveg osztható meg.
A rugalmasabbak számtalan HTML címkét támogatnak, CSS-t, esetleg korlátozott JavaScript-et is.

### Blog.hu

* https://blog.hu/
* Felvásárolta ezt: blogol.hu
* Indamedia Network Zrt. csoport tagja (IndaPass), szolgáltató: Port.hu
* feltölthető fájl
  * jpg, jpeg, gif, png, txt, csv, xls, doc, ppt, css, htm, html, mp3, flv
  * max. 2 MB/db
* egyedi kód
  * https://segitseg.blog.hu/2014/07/29/megujult_sablonszerkeszto
  * https://segitseg.blog.hu/2012/04/01/hogyan_tudok_tetszoleges_html_tartalmaz_berakni_az_oldaldobozokhoz
  * egyedi HTML és CSS
  * JavaScript kód is beszúrható
* aldomain: *.blog.hu
* nincs CORS sem az oldalon, sem RSS-en

### Blogger.hu

* https://blogger.hu/regisztracio
* üzemeltető: Epicenter Market Limited, Anglia
* infrastruktúra: World Web Data Kft.?
* tárhely: korlátlan
* további érdekeltségek
  * Chat.hu
  * Data.hu
  * Bringahirado.hu Kezilabda.hu Sporthirado.hu
  * Linkedin.hu
  * Love.hu
  * Talalka.hu
  * myVIP.com
* aldomain: *.blogger.hu
* nincs CORS sem az oldalon, sem RSS-en

### G-Portal.hu

* https://g-portal.hu/gindex.php?pg=15&qid=5790206
  * https://gportal.hu/
* 300MB tárhely
  * max. 1.5MB/képtár fájl (gif, png, jpeg, swf)
  * médiatár
    * max. 16 MB/fájl
    * feltölthető számtalan dokumentum és multimédia is
  * iframe, CSS, JavaScript részletek
  * http://g-portal.hu/gindex.php?pg=15&qid=5790277
  * http://g-portal.hu/gindex.php?pg=15&qid=5790281
* üzemeltető: Egonet Kft.
* további szolgáltatás: gmail.hu (g-mail.hu)
* aldomain: *.gportal.hu
* nincs CORS sem az oldalon, sem RSS-en

### Reblog.hu

* https://reblog.hu/
* üzemeltető: New Wave Media Group Kommunikációs és Szolgáltató Kft.
* további érdekeltségek
  * videa.hu
  * videakid.hu
  * videaloop.hu
* aldomain: *.reblog.hu
* nincs CORS az oldalra de van az RSS-re

## Magyar ISP

Otthoni, háztartási internet hozzáférési előfizetés mellé gyakran jár (járt) felár nélkül számtalan publikus többletszolgáltatás, mint például: weboldal kiszolgálása, email cím.
Ezek sajnos "elkoptak".

### BorsodWeb ISP

* https://www.borsodweb.hu/images/article/186/J.%20Internet-hozz%C3%A1f%C3%A9r%C3%A9si%20szolg%C3%A1ltat%C3%A1sok%20le%C3%ADr%C3%B3%20t%C3%A1bl%C3%A1zata_(A)%20t%C3%A1bl%C3%A1zat.pdf
* https://www.borsodweb.hu/images/article/191/ASZF_2022.05.01_Internet_TV.pdf
* 20MB webtárhely
* http://xxxxxx.borsodweb.hu/
* email postafiók: xxxxxx@borsodweb.hu

### CellKabel ISP

* Celldömölki Kábeltelevízió Kft.
* https://cellkabel.hu/documents/aszf_internet_2020_11_01_kivonat.pdf
* 50-100MB tárhely
  * http://xxxxxx.cellkabel.hu/
* email
  * https://cellkabel.hu/levelezes
  * 1-3 email postafiók
  * xxxxxx@cellkabel.hu

### Digi.hu ISP

* https://digi.hu/sites/default/files/dokumentumtar/pdf/altalanos/digiugyfelkapu_segedlet_2021_v2.pdf
* 30MB tárhely
* azonos domain alatti almappa
  * `http://w3\.hdsnet\.hu/[a-z0-9_-]{1,25}/`
* dinamikus DNS: a-b-c-d.static.hdsnet.hu
* email postafiók is igényelhető
  * `[a-z0-9_-]{1,64}@digikabel.hu`
  * a fiókra bejövő levelek átirányítása külső címre
* nginx
* privát FTP hozzáférés
* nincs https
* SSI/shtml tiltva
* egyéni hibaoldalak nincsenek
* naplófájlok elérése nincs
* van könyvtárlistázás
* nincs CORS

### Externet ISP

* https://www.externet.hu/ugyintezes/dokumentumok-segedletek-aszf/otthoni-elofizetoi-szerzodesek
* 50MB webtárhely
  * http://yhosts.externet.hu/xxxxxx/
* 3db email cím, 20MB postafiókméret, alias
  * xxxxxx@mail.externet.hu

### HWR Telecom ISP

* https://hwr.hu/wp-content/uploads/2022/03/HWR-Telecom-Kft._Internet_ASZF_2022.04.20.pdf
* FTP
  * 100-500MB tárhely
  * http://web.hwr.hu/xxxxxx
* 5-20db email cím
  * xxxxxx@hwr.hu

### jacsa.net ISP

* http://www.jacsa.net/cms/content/view/13/26/
* "C" internetcsomag vagy afelett
  * min. 500MB
  * Apache, PHP, Python, MySQL
  * korlátlan számú postafiók
  * TLS
  * SFTP feltöltés
  * kérésre SSH
  * saját domain
    * https://ipinfo.io/AS197112#block-domains
* email cím:
  * min. 2 fiók
  * 100MB tárhely/fiók
  * xxxx@jacsanet.hu

### NordTelekom ISP

* http://nordtelekom.hu/detail.php?p=759&ih=1
* 100MB webtárhely
  * http://web.nordtelekom.hu/xxxxxx
* 5db email cím
  * xxxxxx@nordtelekom.hu

### SzivarvanyNet ISP

* https://www.szivarvanynet.hu/lakossagi+dijcsomagok.html
* 2GB tárhely
* 5db email cím (5 * 10GB postafiók méret)

### Techno-Tel.hu ISP

* https://www.techno-tel.hu/internet/mikrohullamu-vezetek-nelkuli
* honlap
  * 50MB tárhely
  * 1 aldomain
  * http://xxxxx.technotel.hu/
* 5 email postafiók
  * 25MB tárhely
  * xxxxx@mail.techno-tel.hu
  * xxxxx@techno-tel.hu

### Tarr ISP

* xxxxx@tolna.net
* webtárhely
  * FTP
  * http://www.tolna.net/~xxxxx

### TVnetwork.hu ISP

* http://www.tvnetwork.hu/egyeni/akciok/szolgaltatas_net_csomagok.html
  * http://www.tvnetwork.hu/?action=statikus.view&name=signet_dij
* 20-500MB webtárhely
  * http://web.tvnetwork.hu/xxxxxx/
  * http://web.tvnetwork.hu/~xxxxxx/
* 1db email cím
  * 500MB postafiók
  * email xxxxxx@tvnetwork.hu

## Magyar megszűnt

### BlogTer

* http://blogter.hu/
  * http://blogter.com/
  * http://wiki.archiveteam.org/index.php/Blogter.hu
* 2005-2014

### B13

* http://b13.hu/

### CafeBlog

* már nem lehet regisztrálni
* https://cafeblog.hu/
* üzemeltető: Central Médiacsoport Zrt.

### DataTrans ISP

* https://www.datatrans.hu/
* 250 MB FTP tárhely
  * http://xxxxxx.datatrans.hu/
  * csak az üzleti csomagokhoz járt (nem sokkal drágább), de 2022-ben megszűnt ez a lehetőség és kiszervezték külön díjcsomagba
* https://www.datatrans.hu/wp-content/uploads/2021/04/Datatrans-ASZF_20210501.pdf

### Extra.hu

* 1998-2010
* http://wiki.archiveteam.org/index.php/Extra.hu

### FreeBlog.hu

* https://freeblog.hu/
  * http://wiki.archiveteam.org/index.php/Freeblog.hu

### FreeWeb

* 2001-2019, regisztráció azóta megszűnt, de a korábbi oldalak még elérhetők
* http://freeweb.hu/
  * http://wiki.archiveteam.org/index.php/Freeweb.hu
* új tulajdonos: Sas.hu

### ininet.hu

* 2012-2017, azóta ingyenes regisztráció megszűnt
* http://wiki.archiveteam.org/index.php/Ininet.hu

### InterNetMedia

* http://InterNetMedia.hu/

### mlap.hu

* https://mlap.hu/
  * http://mindenkilapja.hu/
  * Bejelentkezési hibát ír, 2018 óta senki nem frissítette a portálját rajta, 2022 óta `HTTP 502 Bad Gateway`
  * grafikus honlapépítővel
  * alapértelmezésben Creative Commons Nevezd meg!-Ne add el!-Így add tovább! 2.5 Magyarország licenc a feltöltött tartalmakra
  * üzemeltető: Belvárosi Hirdető Kft.

### Pr-Telecom ISP

* https://cellkabel.hu/impressum
* megszűnt email: xxxxxx@pr.hu

### Sarok

* http://sarok.org/

### Tar.hu

* 1999-2011
* http://wiki.archiveteam.org/index.php/Tar.hu

### Telekom.hu ISP

* Megszűnt az újak igénylése: 2018-09-01, de a korábbi ügyfeleknek még üzemeltetik
* https://www.telekom.hu/lakossagi/ugyintezes/gyakori-kerdesek/1909/hogyan_erhetem_el_a_webtarhelyem_
* `http://web.t-online.hu/xxxxx/index.html`
* CGI engedélyezve: `public_html/cgi-bin/*`
* 50MB tárhely
* privát FTP hozzáférés
  * ftp://ftp.t-online.hu
* email
  * 500MB tárhely
  * https://www.telekom.hu/lakossagi/szolgaltatasok/mobil/kapcsolodo-szolgaltatasok/uzenetkuldes/t-email

### UltraWeb

* 2002-2020, azóta az ingyenes szolgáltatás megszűnt
* http://www.ultraweb.hu/
  * http://wiki.archiveteam.org/index.php/Ultraweb.hu

### UPC.hu ISP

* Megszűnt: ~2020-11-01 nagyjából a Vodafone felvásárlással együtt
* https://www.upc.hu/pdf/aszf/kozlemeny_ASZF_20200324.pdf (404)
  * https://24.hu/tech/2021/02/02/vodafone-upc-email-level-meghosszabbitas-webtarhely/
* 10MB tárhely
* email
* http://members.chello.hu/azonosito (404)
* http://members.upclive.hu/azonosito (404)

### X3.hu

* 2000-2011
* http://wiki.archiveteam.org/index.php/X3.hu

### XFree.hu

* A regisztrációs űrlap már nem működik
* https://xfree.hu/
* üzemeltető: TVN.HU Kft.

## Külföldi tárhely

Lásd még:

* [service/free-shell-account.md](service/free-shell-account.md)

### FreeHosting.io

* https://www.freehosting.io/hosting
* korlátlan tárhely
* korlátlan forgalom
* ingyen aldomain: *.freesite.vip
* iFastNet partner

### Gnome membership

* https://wiki.gnome.org/MembershipCommittee/MembershipBenefits
* https://foundation.gnome.org/membership/
  * https://circle.gnome.org/
  * https://gitlab.gnome.org/Teams/Circle/-/blob/master/README.md#who-can-apply
* email átirányítás
* Wordpress blog (httsp://blogs.gnome.org/xxxxx/)
  * https://wiki.gnome.org/Infrastructure/NewBlogRequest
  * nincs CORS sem az oldalon, sem RSS-en
* Discourse https://discourse.gnome.org/
* Indico https://events.gnome.org/
  * https://github.com/indico/indico
* Gandi E-Rate kedvezmény domain és tárhely csomagokra
* Rocket.Chat https://chat.gnome.org/
* https://wiki.gnome.org/Infrastructure/NewAccounts
  * NextCloud https://cloud.gnome.org/
  * BigBlueButton https://meet.gnome.org/
  * GitLab https://gitlab.gnome.org/
    * van API CORS
    * GitLab Snippets https://paste.gnome.org/
    * https://gitlab.gnome.org/Infrastructure/static-web
    * https://static.gnome.org/
      * van CORS
  * ssh
  * statikus webtárhely megszűnt
    * https://mail.gnome.org/archives/desktop-devel-list/2022-March/msg00004.html
    * https://people.gnome.org/~xxxxx/

> Please don't request a GNOME (LDAP) Account unless you have contributed to an existing GNOME project for a medium/long term period of time.
> Developers who need to directly commit code to modules in the core GNOME GitLab group
> Contributors who need to use services which are restricted to GNOME accounts owners. This includes Nextcloud, Openshift and meet.gnome.org.

### ichi.city

* https://ichi.city/
* TLS
* aldomain *.ichi.city
* SFTP feltöltés
* van CORS

### kintohub.com

* https://www.kintohub.com/pricing/
* 1GB tárhely
* 10GB/hó forgalom
* 3000 perc CI/CD
* 512MB RAM
* alszik

### Ubuntu membership

* https://wiki.ubuntu.com/Membership#The_Perks
  * https://wiki.ubuntu.com/PeopleUbuntuCom
  * https://people.ubuntu.com/~username/
* 1GB webtárhely: SFTP, Apache
* blog
* 1 email átirányítás
* Libera.Chat IRC cloak (álnév)
* Ubuntu Advanage (livepatches)
* domén regisztrációs kedvezmény
* nincs CORS sem az oldalon, sem RSS-en

> Use of this service should be with the aim of helping Ubuntu in some way

### uCoz

* https://www.ucoz.hu/pricing/
* magyar felület
* 400MB tárhely
* üzemeltető: uCoz Media (Mail.ru csoport), Oroszország
* FTP feltöltés
* Kombinálható, CMS komponensek
  * szerver oldali JavaScript (TODO???)
* nincs TLS
* aldomain: *.ucoz.hu *.ucoz.com
* nincs CORS sem az oldalon, sem RSS-en

### GitLab

* https://docs.gitlab.com/ee/user/project/pages/
* 10GB tárhely https://about.gitlab.com/blog/2015/04/08/gitlab-dot-com-storage-limit-raised-to-10gb-per-repo/
* rugalmas CI
* van CORS

### GitHub

* https://pages.github.com/
* https://docs.github.com/en/github/working-with-github-pages/about-github-pages
* 1GB tárhely
* 100GB/hó forgalom
  * korlátozott lekérésszám (CDN javasolt)
* csak nem-kereskedelmi felhasználásra
  * https://docs.github.com/en/github/site-policy/github-additional-product-terms#4-pages
* CI: Jekyll (esetleg Travis útján más)
* van CORS

### BitBucket

* https://support.atlassian.com/bitbucket-cloud/docs/publishing-a-website-on-bitbucket-cloud/
* 1GB tárhely https://support.atlassian.com/bitbucket-cloud/docs/what-kind-of-limits-do-you-have-on-repositoryfile-size/
* aldomain: *.bitbucket.io
* van CORS

### Netlify

* https://www.netlify.com/pricing/
* 100GB tárhely
* 100GB/hó forgalom
* 300perc/hó CI
  * https://www.netlify.com/products/build/
* 100 beküldütt űrlap/hó
* 1000 azonosított felhasználó/hó
* serverless functions
* SSL
* CDN: CloudFlare
* aldomain: *.netlify.app
* nincs CORS sem az oldalon, sem RSS-en

### gatsbyjs

* https://gatsbyjs.com/pricing#plan-FREE
* 1 egyedi domain
* 100GB/hó forgalom
  * 1M lekérés/hó
  * 100k serverless function/hó
* CI/CD: 1 vCPU, 1GB RAM
* forrás: GitHub, GitLab, BitBucket
* CDN: 33 POPS
* ingyenes kimenet: Netlify és hasonló, illetve saját hozott domain alatt

### Vercel

* https://vercel.com/pricing
* korlátlan tárhely és forgalom
* aldomain: *.vercel.app
* CI
* kedvezmény a fizetős csomagokból szabad szoftveres projekteknek
* serverless functions
* van CORS

### Surge

* https://surge.sh/
* aldomain: *.surge.sh
* CORS fizetős csomagban bekapcsolható https://github.com/surge-sh/example-cors

### MongoDB

* https://www.mongodb.com/pricing
* Shared Clusters adatbázis
* AWS, Azure vagy GCP felhasználásra
* 512MB tárhely

### CodeSandbox

* https://codesandbox.io/s/
* 20MB tárhely
* Maximális fájlméret 7MB
* CDN
* online IDE fejlesztői környezet számos funkcióval

## Külföldi honlapépítő

### carrd.co

* https://carrd.co/
* max. 3 lap ingyen
* aldomain: *.carrd.co *.cdr.co

### TiddlyHost

* https://tiddlyhost.com/
* támogatott: TiddlyWiki, Feather.wiki
* van API CORS amivel lekérhető a JSON!

### jimdo

* https://www.jimdo.com/website/how-to-create/
  * https://help.jimdo.com/hc/en-us/articles/360000205806-Wie-viel-Speicherplatz-und-Bandbreite-habe-ich-zur-Verf%C3%BCgung-
* 500MB tárhely
* 2GB/hó forgalom
* aldomain: *.jimdo.com *.jimdofree.com
* egyedi HTML, CSS
  * fájltípusok: js, gif, jpeg, png, svg, css, pdf, ttf, woff, eot
  * https://help.jimdo.com/hc/en-us/articles/115005512006-Which-file-types-can-I-use-in-the-File-Download-Element-
  * https://funnycat.jimdo.com/en/jimdotutorials-1/change-the-css-of-a-template/
* nincs CORS

### Mozello.com

* https://www.mozello.hu/arak/
* teljesen magyarítva
* aldomain: *.mozello.com
* 500MB tárhely
* ingyen TLS (Cloudflare)
* webshop: 5 termék, 1 termékopció, 5 termékváltozat, PayPal
* üzemeltető: Lettország (Mozello SIA)
* egyedi HTML, CSS és JavaScript
* nincs CORS sem az oldalon, sem RSS-en

### site123

* https://site123.com/pricing#accordion-1213
* magyar felület
* 250MB tárhely
* 250MB/hó forgalom
* aldomain

### StaticSave

* https://staticsave.com/pricing.php
* max. 2 mappa, max. 5 fájl/mappa, max. 30000 karakter/fájl
* inaktivitás esetén törlés
* fájltípusok: CSS, JavaScript, TXT, JSON, XML
* CloudFlare
* TLS
* prefix: static.staticsave.com/content/${USER}/${BASENAME}.css
* van CORS minden fájltípusra

### txti.es

* http://txti.es/
  * http://motherfuckingwebsite.com/
* Csak minimális markdown formázást támogat
* 6 hónap után törli amit kevesebb mint 2 látogató nyitott meg
* nincs CORS

### versoly

* https://versoly.com/pricing
* 3 lap
* 5000 napon belül egyedi látogató/hó
* 50 CMS sor
* 50 űrlapbeküldés
* szerkeszthető HTML, CSS, JS
* kiszolgálás: Amazon AWS
* szemantikus HTML, Tailwind CSS
* TLS
* aldomain: `*.versolyi.page`
* népszerűsíti magát az oldalunkon
* átirányítások

### WebNode.info

* https://www.webnode.info/fizetos-es-ingyenes-szolgaltatasok
* magyar felület (sok helyen gépi fordítás)
* aldomain: *.webnode.hu *.webnode.page *.webnode.fr *.webnode.sk *.webnode.at
* blog CMS
* üzemeltető: Webnode AG, Svájc
* 100MB tárhely
  * 1GB/hó átvitel
  * feltölthető fájlok: képek, dokumentumok, multimédia, egyéb
  * https://www.webnode.info/tartalomszerkesztes/a-webhelyre-feltoltheto-elfogadott-fajlok-listaja
* egyedi HTML
  * egy bejegyzésbe bizonyos HTML címkék beszúrhatók (pl. iframe, JavaScript)
    * https://www.webnode.info/tartalomszerkesztes/hogyan-adj-html-kodot-az-oldaladhoz
  * CSS szerkesztése nem támogatott
    * https://www.webnode.info/szerkeszto-es-tartalom
  * egyedi HTML kód szúrható a fejlécbe és láblécbe is ami JavaScriptet is tartalmazhat
    * https://www.webnode.info/kozossegi-oldalak-es-widgetek/hogyan-illessz-be-facebook-widgetet
* nincs CORS sem az oldalon, sem RSS-en

### Weebly.com

* https://www.weebly.com/pricing
* üzemeltető: Block Inc., USA
* 500MB tárhely
* aldomain: *.weebly.com
* TLS
* egyedi HTML, CSS
* nincs CORS

## Külföldi blog

### Wix.com

* https://www.wix.com/free/web-hosting
* 500MB tárhely
* 500MB/hó forgalom
* HTTPS
* CDN
* weblapszerkesztő, kész sablonok, SEO eszköztár
  * egyedi HTML megengedett
  * beszúrt CSS
  * bizonyos JavaScript funkciók
* ingyenes csomag korlátai: reklámot jelenít meg, csak aldomain
* reklámokat szúr be
* bővítmények
  * https://www.wix.com/app-market
* csak saját domain mellé

### Wordpress.com

* http://wordpress.com/
* blog SaaS
* 3GB tárhely
* Let's Encrypt SSL
* bővítmények
  * Inspiráció egy régi bővítményből: https://wordpress.org/plugins/really-static/
* reklámokat szúr be
* biztonsági mentés
* egyedi HTML
* aldomain: *.wordpress.com
* nincs CORS

### WriteFreely

* https://writefreely.org/instances
  * https://write.as/blog/changing-free-registrations
  * újabban már csak meghívás alapon lehet fiókot regisztrálni, de névtelen bejegyzéseket továbbra is lehet külsősként is írni
  * https://write.as/new
* 1 blog
* 3-15 bejegyzés/nap
* korlátlan megtekintés
* formázás: Markdown, MathJax, szerkesztő
* publikálási API
* RSS olvasás
* van TLS
* prefix: write.as/${USER}/
* ActivityPub
* ingyenesben nincs: beágyazás, statikus oldalak, saját domain, témák
* nincs CORS az oldalra de van az RSS-re

## gemini

### breadpunk.club

* https://breadpunk.club/join/
* gopher, gemini és HTML
* nincs CGI, de igényelhető
* nincs aldomain, csak mappa
* nincs CORS
* van TLS

### yesterweb.org

* https://cities.yesterweb.org/
* csak gemini
* van aldomain: *.cities.yesterweb.org
* nincs CORS
* van CORS: https://zine.yesterweb.org/

### cosmic.voyage

* https://cosmic.voyage/join.html
* gopher, gemini és HTML
* nincs aldomain, csak mappa
* van TLS
* nincs CORS
* blog: közösen költött történet űrexpedícióhoz

### ctrl-c.club

* https://ctrl-c.club/
* gemini://gemini.ctrl-c.club
* gemini, HTML
* nincs aldomain, csak mappa
* nincs CORS
* van TLS

### heathens.club

* https://heathens.club/
* gemini, HTTP
* nincs aldomain, csak mappa
* van TLS
* nincs CORS

### envs.net

* https://envs.net/
* 1GB tárhely
* gopher, gemini, HTML
* van aldomain: *.envs.net
* van TLS
* nincs CORS
* [../server/palette-inspiration.md#envs.net](../server/palette-inspiration.md#envs.net)

### flounder.online

* https://flounder.online/
* van gemini és HTML is
* van aldomain: *.flounder.online
* van TLS
* nincs CORS

### gemlog.blue

* https://gemlog.blue/
* csak gemini alatt van áttekintés, viszont az egyedi bejegyzések formázás nélküli HTTP+gmi alól is elérhetők
* nincs aldomain csak mappa
* csak blog
* van TLS
* nincs CORS

### koyu.space

* gemini://koyu.space/info.gmi
* csak gemini
* nincs aldomain, csak mappa
* a domain alatt Mastodon is fut
* FTP és git tároló alól publikál statikus gmi fájlokat

### midnight.pub

* https://midnight.pub/
* van gemini és HTML is
* nincs aldomain
* blog és hozzászólások
* van TLS
* nincs CORS

### rawtext.club

* https://rawtext.club/sign-up.html
* gopher, gemini, HTML
* nincs aldomain, csak mappa
* van TLS
* nincs CORS, nincs RSS CORS

### SDF

* https://sdf.org/?faq?GOPHER?02
* gopher (csak mappa), HTML (van aldomain, TLS)
* nincs CORS, nincs RSS CORS

### si3t.ch

* https://gmi.si3t.ch/
* csak gemini
* nincs aldomain, csak mappa
* SFTP

### smol.pub

* https://smol.pub/
* van gemini és HTML is
* egyedi CSS támogatva HTML kiszolgálásnál
* van TLS
* van aldomain: *.smol.pub
* nincs CORS az oldalra de van az RSS-re

### tilde.pink

* https://tilde.pink/
* van gemini és HTML is
* van TLS
* nincs aldomain csak mappa
* van CGI
* nincs CORS
* TODO: .htaccess?

### tilde.team

* https://tilde.team/
* van gemini és HTML is
* van TLS
* van aldomain: *.tilde.team
* nincs CORS
* TODO: .htaccess?

### station.martinrue.com

* gemini://station.martinrue.com/
* csak gemini
* nincs aldomain
* blog és hozzászólások

## Nagy szereplők

### Blogger.com

* https://www.blogger.com/
* 15GB tárhely
  * max. 1MB/oldal
* bizonyos korlátozások a HTML, CSS, JS testreszabásával kapcsolatban
* üzemeltető: Google
* van TLS
* aldomain: *.blogspot.com
* nincs CORS sem az oldalon, sem RSS-en

### Cloudflare Pages

* https://pages.cloudflare.com/
* támogatott a manuális feltöltés és GitHub/GitHub CI is
* korlátlan forgalom
* CDN
* serverless functions
  * https://workers.cloudflare.com/
* van TLS
* aldomain: *.pages.dev
* van CORS

### Firebase

* https://firebase.google.com/pricing/
* 10GB tárhely, 360MB/nap forgalom
* Firestore (szinkronizált NoSQL dokumentumtár): 1GB tár, 10GB/hó letöltési forgalom, 20k dokumentumírás/nap
* Firebase realtime database (valós időben kliensekkel szinkronizált): 1GB tár, 10GB/hó letöltés
* Firebase Storage (GCP bucket): 5GB tár, 1GB/nap letöltés, 20K/nap feltöltés
* üzemeltető: Google

### Google Sites

* https://en.wikipedia.org/wiki/Google_Sites
* weblapszerkesztő
* Classic
  * 100MB tárhely (független Google Drive-től)
    * max. 50MB csatolmány
  * 10 új létrehozható portál 5 napos csúszóablakkal
    * korlátlan oldalszám
* üzemeltető: Google
* nincs aldomain
* prefix: sites.google.com/site/${USER}
* nincs CORS

### Tumblr

* https://en.wikipedia.org/wiki/Tumblr
* korlátlan tárhely
* üzemeltető: Automattic, USA
* egyedi HTML, CSS, JavaScript
* aldomain: *.tumblr.com
* nincs CORS sem az oldalon, sem RSS-en

## Megszűnt

### circumlunar.space

* https://gemini.circumlunar.space/news/2023_01_14.gmi
* gemini://gemini.circumlunar.space/users/
* már nem él az ajánlat, email megkeresés alapján ment
* csak gemini
* nincs aldomain csak mappa

### srht.site

* gemini://srht.site/
* https://sourcehut.org/pricing/
* gemini, HTML
* 1GB tárhely
* van aldomain: *.srht.site
* új tárolók létrehozása nem ingyenes
* újabban már nem jönnek be alóla gemini oldalak

### Egyéb megszűnt

* EzyWebs
* https://pollux.casa/
