# Ingyenes statikus webtárhely

Egyes szoftver projekt tárolóknak is része a statikus webkiszolgálás és a CI/CD amivel honlapgenerálás is megvalósítható:

* [service/free-vcs-code-hosting.md](service/free-vcs-code-hosting.md)

## Keretrendszerek

* https://en.wikipedia.org/wiki/Category:Static_website_generators
* https://en.wikipedia.org/wiki/Category:Free_static_website_generators
* https://en.wikipedia.org/wiki/Web_template_system#Static_site_generators
* https://en.wikipedia.org/wiki/Static_web_page
* https://staticadventures.netlib.re/blog/entering-the-static-web/

## Magyar tárhely

Támogat tetszőleges HTML dokumentumok, benne CSS és JavaScript közzétételét.
Teljes HTML testreszabást ad.
Tipikusan FTP klienssel is feltölthető.
A kiszolgált oldal legfeljebb reklámbeszúrásban térhet el.

### DotRoll

* https://dotroll.com/hu/szolgaltatasok/tarhely/
* 50MB tárhely
* FTP feltöltés

### IngyenWeb

* http://www.ingyenweb.hu/
* 200MB tárhely
* FTP feltöltés

## Magyar honlapépítő

FTP hozzáférést és teljes HTML testreszabást nem ad.

### 5mp.eu

* tulajdonos: Gáspár György EV
* infrastruktúra: Revo Systems Kft.
* 10MB tárhely
* reklámot helyez el
* nincs fájlfeltöltés

### eOldal.hu

* https://www.eoldal.hu/
* 200MB tárhely
* tulajdonos: Central Médiacsoport Zrt.
* infrastruktúra: Websitemaster a.s. a NETHOST s.r.o., Csehország
* legalább 3 havonta be kell lépni az adminisztrációs felületre

### ewk.hu

* https://ewk.hu/
* tulajdonos: Vilmányi Gergő EV, Vilmányi Xénia EV
* infrastruktúra: NLG-System Bt.
* 50MB tárhely
* nincs fájlfeltöltés
* reklámot helyeznek el

### HuPont.hu

* https://www.hupont.hu/
* tárhely: korlátlan szövegeknek és képeknek
* reklámot helyeznek el
* tulajdonos: Mass Presence Kft.
* infrastruktúra: INTEGRITY Kft. (1132 Budapest, Victor Hugo u. 18-22.)
* nincs fájlfeltöltés
* nincs iframe beágyazás (csak YouTube)
* korlátozott HTML szerkeszthetőség

### ini.hu

* http://ini.hu/
* 30MB tárhely
* 10 email cím
* üzemeltető: Deltha Rendszerház Kft.
* regisztráció csak papíron, levélben vagy faxolva beküldve, évente meg kell újítani!
* reklámokat helyez el

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

### G-Portal.hu

* http://g-portal.hu/gindex.php?pg=15&qid=5790206
* 300MB tárhely
  * max. 1.5MB/képtár fájl (gif, png, jpeg, swf)
  * médiatár
    * max. 16 MB/fájl
    * feltölthető számtalan dokumentum és multimédia is
  * iframe, CSS, JavaScript részletek
  * http://g-portal.hu/gindex.php?pg=15&qid=5790277
  * http://g-portal.hu/gindex.php?pg=15&qid=5790281
* üzemeltető: Egonet Kft.

### Reblog.hu

* https://reblog.hu/
* üzemeltető: New Wave Media Group Kommunikációs és Szolgáltató Kft.
* további érdekeltségek
  * videa.hu
  * videakid.hu
  * videaloop.hu

## Magyar ISP

Otthoni, háztartási internet hozzáférési előfizetés mellé gyakran jár (járt) felár nélkül számtalan publikus többletszolgáltatás, mint például: weboldal kiszolgálása, email cím.
Ezek sajnos "elkoptak".

### Digi.hu ISP

* https://digi.hu/sites/default/files/dokumentumtar/pdf/altalanos/digiugyfelkapu_segedlet_2021_v2.pdf
* 30MB tárhely
* azonos domain alatti almappa
  * `http://w3\.hdsnet\.hu/[a-z0-9_-]{1,25}/`
* email postafiók is igényelhető
  * `[a-z0-9_-]{1,64}@digikabel.hu`
  * a fiókra bejövő levelek átirányítása külső címre
* nginx
* privát FTP hozzáférés
* nincs https
* SSI/shtml tiltva
* egyéni hibaoldalak nincsenek
* naplófájlok elérése nincs

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

### Techno-Tel.hu ISP

* https://www.techno-tel.hu/internet/mikrohullamu-vezetek-nelkuli
* honlap
  * 50MB tárhely
  * 1 aldomain
  *  http://xxxxx.technotel.hu/
* 5 email postafiók
  * 25MB tárhely

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
* ingyen freesite.vip aldomain
* iFastNet partner

### uCoz

* https://www.ucoz.hu/pricing/
* magyar felület
* 400MB tárhely
* üzemeltető: uCoz Media (Mail.ru csoport), Oroszország
* FTP feltöltés
* Kombinálható, CMS komponensek
  * szerver oldali JavaScript (TODO???)

### GitLab

* https://docs.gitlab.com/ee/user/project/pages/
* 10GB tárhely https://about.gitlab.com/blog/2015/04/08/gitlab-dot-com-storage-limit-raised-to-10gb-per-repo/
* rugalmas CI

### GitHub

* https://pages.github.com/
* https://docs.github.com/en/github/working-with-github-pages/about-github-pages
* 1GB tárhely
* 100GB/hó forgalom
  * korlátozott lekérésszám (CDN javasolt)
* csak nem-kereskedelmi felhasználásra
  * https://docs.github.com/en/github/site-policy/github-additional-product-terms#4-pages
* CI: Jekyll (esetleg Travis útján más)

### BitBucket

* https://support.atlassian.com/bitbucket-cloud/docs/publishing-a-website-on-bitbucket-cloud/
* 1GB tárhely https://support.atlassian.com/bitbucket-cloud/docs/what-kind-of-limits-do-you-have-on-repositoryfile-size/

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

### Vercel

* https://vercel.com/pricing
* korlátlan tárhely és forgalom
* CI
* kedvezmény a fizetős csomagokból szabad szoftveres projekteknek
* serverless functions

### Surge

* https://surge.sh/

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

### WebNode.info

* https://www.webnode.info/fizetos-es-ingyenes-szolgaltatasok
* magyar felület (sok helyen gépi fordítás)
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

### Weebly.com

* https://www.weebly.com/pricing
* üzemeltető: Block Inc., USA
* 500MB tárhely
* TLS
* egyedi HTML, CSS

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

## Nagy szereplők

### Blogger.com

* https://www.blogger.com/
* 15GB tárhely
  * max. 1MB/oldal
* bizonyos korlátozások a HTML, CSS, JS testreszabásával kapcsolatban
* üzemeltető: Google

### Cloudflare Pages

* https://pages.cloudflare.com/
* CI
* korlátlan forgalom
* CDN
* serverless functions
  * https://workers.cloudflare.com/

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

### Tumblr

* https://en.m.wikipedia.org/wiki/Tumblr
* korlátlan tárhely
* üzemeltető: Automattic, USA
* egyedi HTML, CSS, JavaScript
