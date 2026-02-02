# Web search engines

See also:

* [../server/backend-optional-portal-search.md](../server/backend-optional-portal-search.md)

## Concept

You may be tempted to proxy your queries towards a monopolist through a metasearch engine.
Here are some reasons why this is not desirable:

* Profile through correlation via timing, typos, some other property of successive queries or the phrase itself
* You may accidentally copy & paste personal data
* Every search you execute may finance the upstream search provider directly by way of commission
* You help improve the upstream search provider by providing input to popularity, phrases, parsing, query refinement and result ranking
* You are not helping improve the competitors by withholding these crowdsourced inputs

## Small web

### GopherVista

* http://gophervista.benjojo.co.uk/query?pg=q&what=0&q=gopher&search.x=0&search.y=0
* https://github.com/benjojo/gophervista

Gemini:

### Auragem

* gemini://auragem.ddns.net/search/s?gemini
* gemini://auragem.letz.dev/search/s?gemini
* https://gitlab.com/clseibold/auragem_sis
* https://web.archive.org/web/20241009014158/https://gitlab.com/clseibold/auragem_crawler

### Gemplex

* gemini://gemplex.space/search?gemini
* https://github.com/elektito/gemplex

### Kennedy

* gemini://kennedy.gemi.dev/search?gemini
* https://github.com/acidus99/Kennedy

### TLGS

* gemini://tlgs.one/
* https://tlgs.one/
* gemini://auragemhkzsr5rowsaxauti6yhinsaa43wjtcqxhh7fw5tijdoqbreyd.onion/
* https://github.com/marty1885/tlgs

## Independent with index

### activesearchresults.com

* https://www.activesearchresults.com/searchsubmit.php
* own index
* can be used without JavaScript

### alexandria.org

* https://www.alexandria.org/
* https://github.com/alexandria-org
* FOSS
* own index
* can be used without JavaScript

### artadosearch.com

* https://www.artadosearch.com/search?Button1=Artado&i=test
* own index
* can be used without JavaScript (by typing in the search query in the URL)

### base-search.net

* DE
* https://www.base-search.net/
* own index of academical publication
* can be used without JavaScript

### blog-search.com

* https://www.blog-search.com/cgi-bin/search.cgi
* source: ExactSeek.com
* can be used without JavaScript

### brave.com

* US
* https://search.brave.com
* can be used without JavaScript
* own index
* the search result description seems to be generated from the beginning of the static HTML (Brave)

### clew.se

* US
* https://clew.se/search?q=
* https://codeberg.org/Clew
* FOSS frontend and backend (except crawler)
* can be used without JavaScript
* own index

### curlie.org

* https://curlie.org/search
* can be used without JavaScript
* own index

### exactseek.com

* Canada
* https://www.exactseek.com/cgi-bin/search.cgi?sub=Search&q=indexer
* can be used without JavaScript
* own index

### ichi.do

* https://ichi.do/search?q=
* can be used without JavaScript
* own index
* host: AWS

### infotiger.com

* https://infotiger.com/
* can be used without JavaScript
* own index
* also offers a Tor onion address

### jambot.com

* https://jambot.com/se?query=
* can be used without JavaScript
* own index

### kukei.eu

* https://kukei.eu/?q=gemini
* can be used without JavaScript
* own index

### marginalia-search.com

* https://marginalia-search.com/
* FOSS, can also be self-hosted
* requires Anubis with JavaScript
* own index

### old-search.marginalia.nu

* https://old-search.marginalia.nu/search?query=gemini&js=&adtech=&searchTitle=&profile=&recent=
* FOSS, can also be self-hosted
* can be used without JavaScript
* own index

Source code:

* https://github.com/MarginaliaSearch/MarginaliaSearch
* https://git.marginalia.nu/marginalia/marginalia.nu

Downloadable database dumps:

* https://downloads.marginalia.nu/exports/
* https://github.com/MarginaliaSearch/PublicData

### MetaGer

* https://metager.org/search-engine
* https://gitlab.metager.de/open-source/MetaGer
* DE
* paid Service
* own index: Scopia 
* metasearch: Bing, Mojeek, Brave, Serper (Google), Pixabay, OneNewspage, Ebay, Minisucher Wissenschaft, TUBdok, BASE
* returns results within an iframe - opening the link directly allows viewing the results without JavaScript
* https://github.com/bkil/static-wonders.js/blob/master/userjs/metager.de.user.js
* option to open result hits through their proxy
* the search result description seems to be a subset of DuckDuckGo

### Mojeek

* https://mojeek.com/
* GB
* can be used without JavaScript
* own index
* the search result description seems to be unique

### mwmbl.org

* https://mwmbl.org/
* https://github.com/mwmbl/mwmbl
* FOSS
* can be used without JavaScript
* own index
* the search result description seems to be generated from an interesting continuous part of the static HTML (mwmbl)

### naver.com

* https://search.naver.com/search.naver?where=nexearch&sm=top_hty&fbm=0&ie=utf8&query=
* Korea
* own index
* can be used without JavaScript

### oldavista

* http://oldavista.com/
* can be used without JavaScript
* own index
* mostly focuses on archived versions of classic web pages

### Qwant.com

* https://www.qwant.com/
* FR
* has its own index
* also uses Bing
* requires JavaScript
* shows a CAPTCHA if searching for too long strings
* the search result description does not match Bing, seems to be faithfully summarized

### rightdao.com

* https://rightdao.com/
* can be used without JavaScript
* own index

### search.ch

* https://search.ch/
* can only find pages hosted in Switzerland
* can be used without JavaScript

### searchcode.com

* https://searchcode.com/
* can be used without JavaScript
* only indexes program source code

### searchmysite.net

* https://searchmysite.net/
* can be used without JavaScript
* own index, a website can only be added after a subscription

### search.seznam.cz

* https://search.seznam.cz/
* Czech
* can be used without JavaScript
* own index
* the search result description seems to be unique

### secretsearchenginelabs.com

* http://www.secretsearchenginelabs.com/find/
* own index
* can be used without JavaScript

### stract.com

* https://stract.com/search
* https://github.com/StractOrg/stract
* FOSS
* can be used without JavaScript
* own index

### webcrawler.com

* https://www.webcrawler.com/serp
* can be used without JavaScript
* own index
* the search result description seems to match Startpage

### wibyweb

* https://github.com/wibyweb/wiby/
* FOSS
* https://wiby.me/
* can be used without JavaScript
* own index

### YaCy

* https://en.wikipedia.org/wiki/Yacy
* FOSS
* https://yacy.searchlab.eu/yacysearch.html?query=yacy
* can be used without JavaScript
* own index
* the search result description seems to be generated from certain boring parts from the beginning of the static HTML (YaCy)

### yessle.com

* https://www.yessle.com/index.php?keyword=
* own index
* can be used without JavaScript

## Worrisome with index

### greppr.org

* https://greppr.org/
* own index
* requires JavaScript

### plumb.one

* https://plumb.one/results/?q=index
* own index
* requires JavaScript

### seekport.com

* https://www.seekport.com/?language=en&q=
* own index
* requires JavaScript

### svmetasearch.eu.org

* Poland
* https://svmetasearch.eu.org/s/search
* https://codeberg.org/SVWareHouse/SVMetaSearch
* FOSS
* SearxNG metasearch: Qwant, Yahoo, Wikipedia, Wikidata
* also own index (sometimes times out)
* can be used without JavaScript

### sese.yyj.moe

* https://github.com/RimoChan/sese-engine
* https://github.com/YunYouJun/sese-engine-ui
* https://sese.yyj.moe/search?q=
* FOSS
* own index
* requires JavaScript

### vyntr.com

* https://vyntr.com/
* https://github.com/outpoot/vyntr
* FOSS
* own index
* requires JavaScript

### yep.com

* https://yep.com/web
* requires JavaScript
* own index
* the search result description seems to be generated from a combination of the beginning and an interesting part of the static HTML (yep)

## Independent proxy

### dogpile.com

* https://www.dogpile.com/serp?q=
* can be used without JavaScript
* source: Bing
* Infospace Holdings LLC, a System1 Company
* the search result description seems to match Bing

### ecosia.org

* DE
* https://www.ecosia.org/
* source: Bing
* can be used without JavaScript
* the search result description does not match Bing, seems to be faithfully summarized

### etools.ch

* https://www.etools.ch/
* metasearch engine: Base, Bing, Brave, DuckDuckGo, Google, Lilo, Mojeek, Qwant, Search, Tiger, Wikipedia, Yahoo, Yandex
* can be used without JavaScript
* the search result description seems to match a subset of Bing

### excite.com

* https://results.excite.com/serp?q=
* can be used without JavaScript
* source: Bing
* the search result description seems to match Bing

### frogfind.com

* http://www.frogfind.com/
* can be used without JavaScript
* source: DuckDuckGo
* the search result description seems to match DuckDuckGo

### ghosterysearch.com

* https://ghosterysearch.com/search?q=
* can be used without JavaScript
* search result descriptions seem to match Brave

### good-search.org

* https://good-search.org/en/search/?q=
* DE
* can be used without JavaScript
* source: Bing (?)
* search result descriptions seem to match Brave

### search.lilo.org

* https://search.lilo.org/?q=
* source: Bing
* can be used without JavaScript
* the search result description seems to match a subset of Bing

### metacrawler.com

* https://www.metacrawler.com/serp?q=
* can be used without JavaScript
* source: Bing
* the search result description seems to match Bing

### monocles.eu

* https://monocles.eu/
* DE
* can be used without JavaScript
* Searx
* the search result description seems to match DuckDuckGo

### nona.de

* https://www.nona.de/
* can be used without JavaScript
* source: Bing
* the search result description seems to be unique

### privacywall.org

* https://www.privacywall.org/search/secure/?q=
* can be used without JavaScript
* source: Bing (?)
* the search result description does not match Bing, seems to be generated from the beginning of the static HTML (PrivacyWall)

### Searx

* metasearch engine, does not have a crawler
* https://github.com/searx/searx
* https://github.com/searxng/searxng
* https://searx.neocities.org/nojs
* https://searxng.online/search
* https://searx.nixnet.services/
* FOSS
* can be used without JavaScript

### whoogle.org

* https://whoogle.herokuapp.com/
* https://whoogle.org/
* source: Google
* can be used without JavaScript
* the search result description seems to be summarized with hallucination (Google)

## Monopolist proxy

### DuckDuckGo.com

* https://lite.duckduckgo.com/lite/
* USA
* source: Bing (formerly: also Yandex)
* TODO: own index
* can be used without JavaScript
* shows a custom form and image-based CAPTCHA if searching too fast or for long strings, it can be solved without JavaScript
* the search result description seems to be summarized twice with hallucination: one custom and one coming from Bing (DuckDuckGo)

### lycos.com

* https://search11.lycos.com/web/?q=
* can be used without JavaScript
* source: Yahoo (Bing)
* the search result description seems to match Bing

### Startpage

* http://startpage.com/
* NL
* owned by adtech company System1
* source: Bing (formerly: Google)
* formerly: lxquick
* the search result description does not match Bing: seems to be generated from an interesting part of the static HTML (StartPage)
* prescribes the use of JavaScript, but results are actually visible with the following CSS addition:

```
#root {
  opacity: initial;
}
```

## Worrisome proxy

### 4get.ca

* https://4get.ca/
* https://4get.ca/instances
* https://4get.maid.zone/
* https://4get.aishiteiru.moe/
* metasearch engine: DuckDuckGo, Brave, Yandex, Google, Qwant, Yep, Greppr, Crowdview, mwmbl, mojeek, marginalia, wiby, curlie
* can be used without JavaScript
* need to solve an image ticker CAPTCHA every 100 search queries (FIXME somehow always asks it, maybe due to cookies?), it works without JavaScript or cookies

### alohafind.com

* https://alohafind.com/search/?q=
* requires JavaScript

### crowdview.ai

* https://crowdview.ai/
* requires JavaScript

### ekoru.org

* https://www.ekoru.org/?q=
* source: Yahoo (Bing)
* requires JavaScript

### findx.com

* https://www.findx.com/search?noscript=1&q=
* requires JavaScript
* Source: Bing

### gibiru.com

* https://gibiru.com/
* requires JavaScript

### gmx.com

* https://search.gmx.com/web/result?q=
* requires JavaScript
* source: Google, YouTube

### oceanhero.today

* https://oceanhero.today/web?q=secure
* requires JavaScript
* source: Bing

### presearch.com

* https://presearch.com/
* requires JavaScript

### search.com

* https://www.search.com/
* requires JavaScript

### swisscows.com

* https://www.swisscows.com
* Switzerland
* requires JavaScript
* source: Bing

### tiger.ch

* https://tiger.ch/
* metasearch: Alugha, Ask, Bing, Brave, Dailymotion, DuckDuckGo, Google.ch, Mojeek, Nona, Search.ch, Vimeo, Wiki-Tube.de, Wikipedia, Youtube
* can only find pages hosted in Switzerland
* requires JavaScript

### youcare.world

* https://youcare.world/all?q=
* requires JavaScript

## Self-hosted FOSS

* https://github.com/chatnoir-eu
* https://github.com/capjamesg/indieweb-search
* https://git.mills.io/prologic/spyda
* https://github.com/meilisearch/meilisearch
* https://github.com/typesense/typesense
* https://github.com/presearchofficial
* https://en.wikipedia.org/wiki/Lemur_Project
* https://gitlab.com/users/infinitysearch/projects
* https://github.com/orgs/WordPress/repositories?q=openverse&type=all&language=&sort=
* https://seekseek.org/technology
* https://github.com/gigablast/open-source-search-engine

## Monopolists

### baidu.com

* https://www.baidu.com
* China
* can be used without JavaScript
* will start blocking if you search for the wrong keywords

### bing.com

* https://www.bing.com/
* US
* the search result description seems to be summarized with hallucination (Bing)

### sogou.com

* https://www.sogou.com/web?query=
* China
* can be used without JavaScript

### Yandex.com

* https://www.yandex.com/
* Russia
* can be used without JavaScript
* the search result description seems to be summarized with hallucination (Yandex)

## Image search

* https://en.wikipedia.org/wiki/Reverse_image_search#Application_in_popular_search_systems
* https://en.wikipedia.org/wiki/List_of_CBIR_engines
* https://en.wikipedia.org/wiki/Content-based_image_retrieval#Techniques

## Implementing a crawler

* https://badbot.org/
* https://en.wikipedia.org/wiki/Comparison_of_web_search_engines#Search_crawlers
* https://gist.github.com/JoeyBurzynski/9953198b825b9a8675715220586fb494
* https://github.com/CapnDucks/scripts/blob/master/bot-regex
* https://gist.github.com/JoeyBurzynski/b0b0606e2817158455997797e42e78c7
* https://gist.github.com/gaffling/9ed6a55023530d8440f880958e248ebb
* https://github.com/mbilozub/angular-prerender-test/blob/master/.htaccess
* https://github.com/fabiomb/is_bot/blob/master/is_bot.php
* https://github.com/prescience-data/php-cloaker/blob/master/header.php#L237
* https://github.com/VeliovGroup/ostrio/blob/master/docs/prerendering/nginx.md#simple-proxy-pass
* https://github.com/Thomas--F/BotTracker/blob/master/botlist.txt
* https://github.com/e107inc/e107/blob/master/e107_handlers/user_model.php
* https://github.com/flumono/WP_demo/blob/main/robots.txt
* https://github.com/lesterchan/wp-useronline/blob/master/bots.php
* https://jamesbachini.com/robots-disallow-all/
* https://github.com/monperrus/crawler-user-agents/blob/master/crawler-user-agents.json
* https://stackoverflow.com/questions/20084513/detect-search-crawlers-via-javascript
* https://advancedweb.fr/detecter-les-robots-de-recherche-via-javascript/
* https://community.centminmod.com/threads/blocking-bad-or-aggressive-bots.6433/
* https://github.com/mitchellkrogza/nginx-ultimate-bad-bot-blocker/
* https://seirdy.one/posts/2021/03/10/search-engines-with-own-indexes/
* https://github.com/mwmbl/crawler-extension/blob/main/src/worker.js
* https://github.com/alexmolas/microsearch/blob/main/src/microsearch/engine.py

Crawler roots:

* https://domainsproject.org/
* https://github.com/tb0hdan/domains
* https://github.com/Kukei-eu/spider/blob/914b8dfffc10cb3a948561aef2bf86937d3a0b2e/index-sources.js

## TODO

https://2me.global
https://www.activesearchresults.com
https://www.alltheinternet.com
https://alohafind.com
http://www.amidalla.de (finds websites not pages within websites)
https://www.anoox.com
https://www.aol.ca
https://www.artadosearch.com (Turkish)
https://www.askjeeves.net (now Google)
https://www.base-search.net
https://www.blogsearchengine.org
https://bonzamate.com.au (Australian search engine for and by Australians)
https://breachdirectory.org
https://www.chatnoir.eu
https://www.crawlson.com
https://coccoc.com/search (Vietnamese)
https://www.daum.net (Korean)
https://www.dogpile.com
https://www.donttrack.us (now DuckDuckGo)
https://www.dsearch.com
https://www.entireweb.com
https://www.ekoru.org
https://en-int.seekweb.com (uses many search engines)
https://www.fastbot.de (German)
https://www.findresultsnow.com
https://fireball.de
https://freespoke.com
https://glowstery.com
https://www.gnomit.com (finds websites not pages within websites)
https://www.gogoprivate.com
https://www.goodgopher.com
https://www.homeandgardenideas.com
https://www.hotbot.com
https://info.com
https://infospace.com
https://intelx.io
https://www.izito.ca
http://kaz.kz (Kazakhstanian and Russian)
https://kids.kiddle.co
https://kozmonavt.ml (Russian) (Finds websites not pages within websites)
https://www.lukol.com
https://luxxle.com
https://mail.ru (Russian)
https://www.millionshort.com
https://www.moose.at (German)
https://netzzappen.com
https://www.nona.de
https://northboot.xyz
https://www.nowtopresults.com
https://oceanhero.today (uses Bing)
https://oh-aha.com
https://www.onesearch.com
https://www.oscobo.com
https://www.pdfdrive.com
https://peekier.com
https://plumb.one
https://privacytools.io
https://www.privacywall.org
https://private.sh
https://www.reference.com
https://search.aibull.io
https://www.search.ch (Switzerland)
http://search.thunderstone.com/texis/websearch15 (finds websites not pages within websites)
http://www.search.tl (finds websites not pages within websites)
https://www.searchandshopping.org
https://searchcode.com
https://www.searchforplanet.org
https://searchmysite.net
https://search.carrot2.org
https://search.disconnect.me (now DuckDuckGo)
https://search.disroot.org
https://search.fuckoffgoogle.net (no ads)
https://search.gmx.com/web
https://search.lixialabs.com
https://search.ononoki.org
https://search.sidewalk.com
https://search.thunderstone.com/texis/websearch15
http://www.search.tl
https://search.tosdr.org
http://www.secretsearchenginelabs.com
http://www.seekport.com (German)
https://www.semanticscholar.org (academic PDFs)
https://www.sengine.info (finds websites not pages within websites)
https://www.slzii.com
https://www.sogou.com (Chinese)
https://solofield.net (Japanese)
https://spot.ecloud.global
http://www.suche.tw (German)
https://tiger.ch (German, uses 8 different search engines)
https://togoda.com
https://www.torry.io
https://www.toutiao.com (Chinese)
https://www.visymo.com
https://www.vuhuv.com.tr (Turkish)
https://vulners.com
https://web.search.ch
https://www.wolframalpha.com
https://www.wow.com
https://www.yahoo.com
https://www.yessle.com
https://www.yioop.com
https://you.com
https://youcare.world
https://www.youdao.com (Chinese)
https://www.zapmeta.ca
https://www.whodoyou.com

local=/search.0xcb.dev/
local=/searx.32bitflo.at/
local=/search.activemail.de/
local=/haku.ahmia.fi/
local=/search.ahwx.org/
local=/search.albony.xyz/
local=/alltheinternet.com/
local=/zoek.anchel.nl/
local=/andisearch.com/
local=/recherche.aol.fr/
local=/search.aol.ca/
local=/search.aol.com/
local=/suche.aol.de/
local=/search.azkware.net/
local=/librex.baczek.me/
local=/searx.baczek.me/
local=/baidu.com/
local=/baresearch.org/
local=/search.biboumail.fr/
local=/searx.bissisoft.com/
local=/search.bluelock.org/
local=/boomle.com/
local=/search.bowlman.org/
local=/search.bus-hit.me/
local=/searx.catfluori.de/
local=/sx.catgirl.cloud/
local=/recherche.catmargue.org/
local=/search.aol.co.uk/
local=/websearch.excite.co.jp/
local=/searx.com.au/
local=/librex.yogeshlamichhane.com.np/
local=/copp.gg/
local=/search.cronobox.one/
local=/searx.daetalytica.io/
local=/darmarit.org/
local=/suche.dasnetzundich.de/
local=/search.davidovski.xyz/
local=/whoogle.dcs0.hu/
local=/searx.decatec.de/
local=/search.decentrala.org/
local=/searx.deepak.pro/
local=/search.demoniak.ch/
local=/librex.devol.it/
local=/searx.devol.it/
local=/searxng.diadz.de/
local=/search.disroot.org/
local=/searx.divided-by-zero.eu/
local=/dogpile.com/
local=/searx.dojocasts.com/
local=/search.dojoro.de/
local=/search.dr460nf1r3.org/
local=/searx.dresden.network/
local=/wgl.frail.duckdns.org/
local=/dynabyte.ca/
local=/spot.ecloud.global/
local=/searx.ericaftereric.top/
local=/search.ethibox.fr/
local=/etsi.me/
local=/eulie.de/
local=/searx.everdot.org/
local=/results.excite.com/
local=/search.fascinated.cc/
local=/fireball.de/
local=/searx.foo.li/
local=/searx.forked.io/
local=/searx.fossencdi.org/
local=/whoogle.ftw.lol/
local=/search.funami.tech/
local=/search.garudalinux.org/
local=/search.gcomm.ch/
local=/gibiru.com/
local=/gigablast.com/
local=/searx.gnu.style/
local=/searx.gotrust.de/
local=/gruble.de/
local=/searx.hardwired.link/
local=/whoogle.hostux.net/
local=/seeks.hsbp.org/
local=/search.im-in.space/
local=/search.jpope.org/
local=/jsearch.pw/
local=/searx.juancord.xyz/
local=/kagi.com/
local=/trovu.komun.org/
local=/searx.kvch.me/
local=/search.laksith.dev/
local=/searx.lavatech.top/
local=/search.leptons.xyz/
local=/search.lgbtq.cool/
local=/searx.linux.pizza/
local=/lukol.com/
local=/whoogle.lunar.icu/
local=/search.lvkaszus.pl/
local=/searx.lynnesbian.space/
local=/go.mail.ru/
local=/searx.mastodontech.de/
local=/searx.maxxblow.de/
local=/search.mdosch.de/
local=/metacrawler.com/
local=/metager.de/
local=/metager.org/
local=/metager3.de/
local=/searx.mha.fi/
local=/mijisou.com/
local=/millionshort.com/
local=/search.modalogi.com/
local=/mojeek.com/
local=/spot.murena.io/
local=/mwmbl.org/
local=/searx.mxchange.org/
local=/librex.myroware.eu/
local=/searx.nakhan.net/
local=/searx.namejeff.xyz/
local=/search.nebulacentre.net/
local=/search.neet.works/
local=/searx.netzspielplatz.de/
local=/nibblehole.com/
local=/searxng.nicfab.eu/
local=/searx.nightmare.life/
local=/nigma.eu/
local=/searx.nixnet.services/
local=/searxng.no-logs.com/
local=/whoogle.no-logs.com/
local=/librex.nohost.network/
local=/timdor.noip.me/
local=/northboot.xyz/
local=/search.notrustverify.ch/
local=/null.media/
local=/searx.oakleycord.dev/
local=/offtheradar.info/
local=/search.ononoki.org/
local=/ooglester.com/
local=/searx.openhoofd.nl/
local=/searx.openpandora.org/
local=/search.opentunisia.org/
local=/openworlds.info/
local=/opnxng.com/
local=/oscobo.com/
local=/searx.ouahpiti.info/
local=/searx.ox2.fr/
local=/search.pabloferreiro.es/
local=/paulgo.io/
local=/peekier.com/
local=/perfectpixel.de/
local=/presearch.com/
local=/priv.au/
local=/whoogle.privacydev.net/
local=/search.privacytools.io/
local=/search.in.projectsegfau.lt/
local=/search.projectsegfau.lt/
local=/search.us.projectsegfau.lt/
local=/librex.pufe.org/
local=/lite.qwant.com/
local=/search.rabbit-company.com/
local=/nova.rambler.ru/
local=/searx.rasp.fr/
local=/librex.ratakor.com/
local=/whoogle-search--replitcomreside.repl.co/
local=/search.rhscz.eu/
local=/searx.roflcopter.fr/
local=/wtf.roflcopter.fr/
local=/roteserver.de/
local=/search.rowie.at/
local=/search.rubberverse.xyz/
local=/search.sapti.me/
local=/searchencrypt.com/
local=/searchx.mobi/
local=/searx.bar/
local=/searx.be/
local=/searx.ch/
local=/searx.info/
local=/searx.ir/
local=/searx.ninja/
local=/searx.org/
local=/searx.ro/
local=/searx.ru/
local=/searx.run/
local=/searx.si/
local=/searx.work/
local=/searx.xyz/
local=/searx.semipvt.com/
local=/search.sethforprivacy.com/
local=/searx.sev.monster/
local=/search.seznam.cz/
local=/search.smnz.de/
local=/searx.solusar.de/
local=/searx.sp-codes.de/
local=/search.spaceint.fr/
local=/search.spaeth.me/
local=/search.st8.at/
local=/search.stinpriza.org/
local=/suchfeuer.de/
local=/searx.thefloatinglab.world/
local=/searx.thegreenwebfoundation.org/
local=/searx.tiekoetter.com/
local=/search.tildevarsh.in/
local=/s.tokhmi.xyz/
local=/search.trom.tf/
local=/suche.tromdienste.de/
local=/s.trung.fun/
local=/searx.tuxcloud.net/
local=/unmonito.red/
local=/lx.vern.cc/
local=/wg.vern.cc/
local=/searx.vitanetworks.link/
local=/gowogle.voring.me/
local=/webcrawler.com/
local=/searx.wegeeks.win/
local=/wiby.me/
local=/xo.wtf/
local=/yep.com/
local=/yippy.com/
local=/you.com/
local=/searx.zapashcanon.fr/
local=/searx.zdechov.net/

## Defunct

### geminispace.info

* gemini://geminispace.info/

### ExaLead

* https://www.exalead.com/search/
* FR
* TODO: what other providers does it use?
* can be used without JavaScript

### Gigablast

* https://gigablast.com/
* USA
* FOSS, can also be self-hosted
* requires JavaScript, but copying the `rand=` and `pxb=` values from the HTML source and appending `&fromjs=1&rand=...&opxb=...` to the end shows the results
* https://github.com/bkil/static-wonders.js/blob/master/userjs/gigablast.com.user.js

## References

* https://seirdy.one/posts/2021/03/10/search-engines-with-own-indexes/
* https://thenewleafjournal.com/a-2021-list-of-alternative-search-engines-and-search-resources/
* https://www.searchenginemap.com/
* https://searchengine.party/
* https://en.wikipedia.org/wiki/List_of_academic_databases_and_search_engines
* https://wutsearch.com/
* https://cdn.jsdelivr.net/gh/hagezi/dns-blocklists@latest/dnsmasq/nosafesearch.txt
* https://github.com/nextdns/no-safesearch/blob/main/domains
