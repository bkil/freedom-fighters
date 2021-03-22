# Ingyenes content delivery network

## Független egyéni tartalomra

### Statically

* https://statically.io/
* Egyéni tartalmak forrása:
  * GitHub
  * GitLab
  * Bitbucket
  * WordPress SVN (mag, bővítmények, arculatok)
* Fájltípusok
  * Staticzap
    * GitHub, GitLab, Bitbucket
    * Maximális fájlméret 30MB
    * minifikáció: CSS, JS, SVG, HTML, XML
    * HTML bekötése adategyeztetés után
  * Képek
    * tetszőleges URL alapján
    * Maximális féjlméret 20MB
    * GIF, JPEG, PNG, WebP
* Regisztráció szükséges
* Architektúra:
  * NS1.com
  * CDN: Fastly, CloudFlare, BunnyCDN, (Amazon Cloudfront, Google Cloud CDN?)
* Támogatók: DigitalOcean, dewaweb, WP2Static

### jsDelivr

* https://en.wikipedia.org/wiki/JSDelivr
* Egyéni tartalmak forrása:
  * npm registry
  * GitHub tároló
  * Wordpress bővítmények és arculatok
* Architektúra:
  * Névszerver: NS1.com, ClouDNS
  * CDN: StackPath, fastly, CloudFlare, Quantil
  * feldolgozás: Amazon EC2 (Amsterdam és Frankfurt), Amazon S3

### unpkg

* https://unpkg.com/
* Egyéni tartalmak forrása:
  * npm
* Architektúra:
  * CDN: CloudFlare
  * feldolgozás: Google Cloud

### Cloudinary

* https://cloudinary.com/pricing
* Egyéni tartalmak:
  * Képek és videók
  * maximális fájlméret: 10MB
  * maximális videóméret: 100MB
* 25GB tárhely
* 25GB/hó forgalom
* 25000/hó transzformáció
* CDN: Akamai, Fastly, CloudFront

### ArvanCloud Cloud CDN

* https://www.arvancloud.com/en/products/cdn
* Egyéni tartalmak:
  * 50+50GB/hó forgalom
  * 1M/hó lekérés

### Hostry

* https://hostry.com/products/cdn/
* 10GB/hó forgalom

## Független népszerű tartalmakra

### cdnjs

* https://cdnjs.com/
* Előre megszabott elérhető tartalom:
  * Kb. 4000 projekt
  * JavaScript és CSS könyvtárak
  * Bővítés egyedi elbírálás alapján kérhető:
    * https://github.com/cdnjs/packages/blob/master/CONTRIBUTING.md#creating-a-new-library-on-cdnjs
* CDN: CloudFlare (az URL része)
* Támogatók: DigitalOcean, Algolia, Heroku, Atlassian, Discourse, SolarWinds, Sentry
* Tükrözve:
  * https://cdnjs.toolforge.org/
  * https://cdnjs.net/

### PageCDN

* https://pagecdn.com/pricing
* https://pagecdn.com/public-cdn
* Előre megszabott elérhető tartalom:
  * Kb. 14000 projekt
  * népszerűbb szabad projektek
  * WordPress és bootstrap arculatok
  * fontok
  * képgyűjtemények
* Egyéni tartalmak:
  * Snippets CDN
  * 3kB alatt ingyen

## Rutinkönyvtárak

### BootstrapCDN

* https://en.wikipedia.org/wiki/BootstrapCDN
* BootstrapCDN, Font Awesome, Bootswatch
* CDN: jsDelivr

### jQuery

* https://code.jquery.com/
* jQuery Core, UI, Mobile, Color, QUnit, PEP
* CDN: StackPath

### Arvan Library

* https://lib.arvancloud.com/en
* Előre megszabott elérhető tartalom:
  * JavaScript, CSS, fontok

## Nagy szereplők

### CloudFlare

* https://www.cloudflare.com/plans/
* Regisztrácíó szükséges
* Egyéni tartalmak:
  * maximális fájlméret 512MB
  * alapértelmezésből a HTML-en és videón kívül a legtöbb kiterjesztést gyorsítótárazza
  * további kiterjesztések engedélyezhetőek a vezérlőpulton

### Google Hosted Libraries

* https://developers.google.com/speed/libraries/
* Előre megszabott elérhető tartalom:
  * CesiumJS, D3.js, Dojo, Ext Core, Hammer.JS, Indefinite Observable, jQuery, jQuery Mobile, jQuery UI, Material Motion, MooTools, Myanmar Tools, Prototype, script.aculo.us, Shaka Player, SPF, SWFObject, three.js, Web Font Loader

### Microsoft Ajax CDN

* https://docs.microsoft.com/en-us/aspnet/ajax/cdn/overview#Third-Party_Files_on_the_CDN_23
* Előre megszabott elérhető tartalom:
  * jQuery, Modernizr, JSHint, Knockout, Globalize, Respond, Bootstrap, Hammer.js, ASP.NET MVC, SignalR
