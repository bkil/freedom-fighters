# Ingyenes statikus webtárhely

## Keretrendszerek

* https://en.wikipedia.org/wiki/Category:Static_website_generators
* https://en.wikipedia.org/wiki/Category:Free_static_website_generators
* https://en.wikipedia.org/wiki/Web_template_system#Static_site_generators
* https://en.wikipedia.org/wiki/Static_web_page

## Magyar

* https://dotroll.com/hu/szolgaltatasok/tarhely/ 50MB
* http://www.ingyenweb.hu/ 200MB
* https://www.ucoz.hu/pricing/ 400MB
* blog.hu TODO

## Magyar ISP

Otthoni, háztartási internet hozzáférési előfizetés mellé gyakran jár (járt) számtalan publikus többletszolgáltatás, mint például: weboldal kiszolgálása, email cím.
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

### jacsa.net

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

### Techno-Tel.hu

* https://www.techno-tel.hu/internet/mikrohullamu-vezetek-nelkuli
* honlap
  * 50MB tárhely
  * 1 aldomain
  *  http://xxxxx.technotel.hu/
* 5 email postafiók
  * 25MB tárhely

## Magyar megszűnt

### Telekom.hu ISP

* Megszűnt az újak igénylése: 2018-09-01, de a korábbi ügyfeleknek még üzemeltetik
* https://www.telekom.hu/lakossagi/ugyintezes/gyakori-kerdesek/1909/hogyan_erhetem_el_a_webtarhelyem_
* `http://web.t-online.hu/.../index.html`
* CGI engedélyezve: `public_html/cgi-bin/*`
* 50MB tárhely
* privát FTP hozzáférés
  * ftp://ftp.t-online.hu
* email
  * 500MB tárhely
  * https://www.telekom.hu/lakossagi/szolgaltatasok/mobil/kapcsolodo-szolgaltatasok/uzenetkuldes/t-email

### mlap.hu

* https://mlap.hu/
  * http://mindenkilapja.hu/
  * Bejelentkezési hibát ír, 2018 óta senki nem frissítette a portálját rajta
  * grafikus honlapépítővel
  * alapértelmezésben Creative Commons Nevezd meg!-Ne add el!-Így add tovább! 2.5 Magyarország licenc a feltöltött tartalmakra
  * üzemeltető: Belvárosi Hirdető Kft.

### UPC.hu ISP

* Megszűnt: ~2021-11-01 nagyjából a Vodafone felvásárlással együtt
* https://www.upc.hu/pdf/aszf/kozlemeny_ASZF_20200324.pdf (404)
* 10MB tárhely
* email
* http://members.chello.hu/azonosito (404)
* http://members.upclive.hu/azonosito (404)

## Külföldi

Lásd még:

* [service/free-shell-account.md](service/free-shell-account.md)

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

### Wordpress.com

* http://wordpress.com/
* blog SaaS
* 3GB tárhely
* Let's Encrypt SSL
* Inspiráció egy régi bővítményből: https://wordpress.org/plugins/really-static/

### Wix.com

* https://www.wix.com/free/web-hosting
* 500MB tárhely
* 500MB/hó forgalom
* HTTPS
* CDN
* weblapszerkesztő, kész sablonok, SEO eszköztár
  * egyedi HTML megengedett
* ingyenes csomag korlátai: reklámot jelenít meg, csak aldomain

### CodeSandbox

* https://codesandbox.io/s/
* 20MB tárhely
* Maximális fájlméret 7MB
* CDN
* online IDE fejlesztői környezet számos funkcióval

## CI/CD

### Agola

* https://agola.io/
* forrás: GitHub, GitLab, gitea, egyéb git tároló

## Nagy szereplők

### Blogger

* https://www.blogger.com/
* 15GB tárhely
  * max. 1MB/oldal
* bizonyos korlátozások a HTML, CSS, JS testreszabásával kapcsolatban

### Cloudflare Pages

* https://pages.cloudflare.com/
* CI
* korlátlan forgalom
* CDN

### Firebase

* https://firebase.google.com/pricing/
* 10GB tárhely, 360MB/nap forgalom
* Firestore (szinkronizált NoSQL dokumentumtár): 1GB tár, 10GB/hó letöltési forgalom, 20k dokumentumírás/nap
* Firebase realtime database (valós időben kliensekkel szinkronizált): 1GB tár, 10GB/hó letöltés
* Firebase Storage (GCP bucket): 5GB tár, 1GB/nap letöltés, 20K/nap feltöltés

### Google Sites

* https://en.wikipedia.org/wiki/Google_Sites
* weblapszerkesztő
* Classic
  * 100MB tárhely (független Google Drive-től)
    * max. 50MB csatolmány
  * 10 új létrehozható portál 5 napos csúszóablakkal
    * korlátlan oldalszám
