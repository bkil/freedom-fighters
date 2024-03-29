# Ingyenes content delivery network

## Független egyéni tartalomra

### surge.sh

* https://surge.sh/
* Fájltípusok
  * HTML, CSS, JS
* Egyéni tartalmak forrása:
  * parancssorból kell deployolni

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

### rawgithack

* https://raw.githack.com/
* Egyéni tartalmak forrása:
  * GitHub
  * Bitbucket
  * GitLab
  * sourcehut
* Architektúra:
  * Szabad szoftver, reprodukálható: Docker, nginx, lua
  * CDN: CloudFlare
* Fájltípusok
  * Minifikáció: JavaScript, CSS
  * HTML
  * Szinte mindent támogat: https://github.com/neoascetic/rawgithack/blob/master/rawgithack.conf#L19
* korlátlan forgalom

### GitCDN

* https://gitcdn.xyz/
* Egyéni tartalmak:
  * forrása: GitHub
* CDN: Cloudflare

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

### Gcore

* https://gcore.com/pricing
* 1TB/hó forgalom
* 1000M kérés/hó
* ingyen TLS tanúsítvány
* regisztrációhoz címadatokat kér és Google reCAPTCHA, de bejelentkezéshez nem

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

### Server Room Video CDN

* https://www.serverroom.net/cdn/pricing/
* 1TB/hó ingyen
* H.264 videók

### Server Room Internet Radio

* https://www.serverroom.net/radio/pricing/
* 32kb/s hang
* Legfeljebb 1000 párhuzamos hallgató
* 1 folyam
* 1Gb/s osztott sávszélesség

### Hostry

* https://hostry.com/products/cdn/
* 10GB/hó forgalom

### Shift8 CDN

* https://shift8cdn.com/compare
* Egyéni tartalmak:
  * 1TB/hó forgalom
  * maximum 2 URL (weboldal)
  * CSS, JS, képek, fontok
* Architektúra
  * Nginx

### AnyoneCDN

* https://www.anyonecdn.com/
* gzip tömörítés
* korlátlan forgalom
* kizárólag HTTPS weboldallal használható a 443-as porton
* CORS
* 30 nap elévülés
* egyedileg jóváhagyott regisztráció
  * kizárt: pornó, szerencsejáték, hang- és videó streaming, letöltések, még el nem készült oldal

### Jetpack

* https://jetpack.com/features/comparison/
* Számos kiegészítő WordPress funkció
* Site Accelerator: alapértelmezetten ki van kapcsolva
* Egyedi tartalok:
  * Képek: gif, jpg, png
  * 80/HTTP, 443/HTTPS portok
  * automatikus webp újratömörítés
* Előre megszabott elérhető tartalom:
  * JavaScript és CSS: WordPress Core, Jetpack, WooCommerce

### QUIC.cloud

* https://quic.cloud/cost/
* 1GB/hó forgalom
* Egyedi tartalmak

### combinatronics

* https://combinatronics.com/
* Egyéni tartalmak:
  * HTML, CSS, JavaScript
  * forrása: GitHub
* az ingyenes csomagban csak 1 PoP

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

### BootCDN

* https://www.bootcdn.cn/
* Előre megszabott elérhető tartalom:
  * Kb. 4000 projekt
  * JavaScript és CSS könyvtárak

### Staticfile CDN

* https://staticfile.org/
* Előre megszabott elérhető tartalmak

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

### UpYun Library

* http://jscdn.upai.com/
* Előre megszabott elérhető tartalom:
  * jQuery, MooTools, Modernizr, Dojo, Ember.js

### Sina App Engine Public Resources

* https://lib.sinaapp.com/
* Előre megszabott elérhető tartalom:
  * angular.js, backbone, bootstrap, dojo, ext-core, highcharts, highstock, jq.mobi, jquery, jquery-mobile, jquery-ui, jquery.cookie, jquery.migrate, jquerytools, json2, lesscss, mootools, prototype, qunit, scriptaculous, swfobject, underscore, webfont, wlige, yui, zepto

### Plyr

* https://github.com/sampotts/plyr#javascript
* CDN: Fastly

## Nagy szereplők

Kritikák:

* https://git.nixnet.services/you/stop_cloudflare/src/branch/master/subfiles/cloudflare-alternatives.md
* https://git.nixnet.services/you/stop_cloudflare/src/branch/master/article.txt

### CloudFlare

* https://www.cloudflare.com/plans/
* Regisztrácíó szükséges
* Egyéni tartalmak:
  * maximális fájlméret 512MB
  * alapértelmezésből a HTML-en és videón kívül a legtöbb kiterjesztést gyorsítótárazza
  * további kiterjesztések engedélyezhetőek a vezérlőpulton
* Kritika
  * https://git.nixnet.services/you/stop_cloudflare/src/branch/master/instructions.md

### Google Hosted Libraries

* https://developers.google.com/speed/libraries/
* Előre megszabott elérhető tartalom:
  * CesiumJS, D3.js, Dojo, Ext Core, Hammer.JS, Indefinite Observable, jQuery, jQuery Mobile, jQuery UI, Material Motion, MooTools, Myanmar Tools, Prototype, script.aculo.us, Shaka Player, SPF, SWFObject, three.js, Web Font Loader

### Microsoft Ajax CDN

* https://docs.microsoft.com/en-us/aspnet/ajax/cdn/overview#Third-Party_Files_on_the_CDN_23
* Előre megszabott elérhető tartalom:
  * jQuery, Modernizr, JSHint, Knockout, Globalize, Respond, Bootstrap, Hammer.js, ASP.NET MVC, SignalR

### Yandex

* https://yandex.ru/dev/jslibs/
* Előre megszabott elérhető tartalom:
  * bem-components, bem-core, Yandex.Maps, jQuery, Lo-Dash, SWFObject

### baidustatic CDN

* https://github.com/liangmingyi/baidu-cdn-data
* http://libs.baidu.com/
