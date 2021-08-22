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

## Külföldi

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
