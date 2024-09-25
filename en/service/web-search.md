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

Gopher:

* http://gophervista.benjojo.co.uk/query?pg=q&what=0&q=gopher&search.x=0&search.y=0

Gemini:

* gemini://auragem.letz.dev/search/s?gemini
* gemini://gemplex.space/search?gemini
* gemini://kennedy.gemi.dev/search?gemini
* gemini://tlgs.one/

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

### Marginalia

* https://search.marginalia.nu/
* FOSS, can also be self-hosted
* https://git.marginalia.nu/marginalia/marginalia.nu
* can be used without JavaScript
* own index

### MetaGer

* http://metager.de/
* https://gitlab.metager.de/open-source/MetaGer
* DE
* paid Service
* own index: Scopia 
* metasearch: Brave, Mojeek, Bing
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

### Qwant.com

* https://www.qwant.com/
* FR
* has its own index
* also uses Bing
* can be used without JavaScript
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
* https://github.com/presearchofficial
* https://en.wikipedia.org/wiki/Lemur_Project
* https://gitlab.com/users/infinitysearch/projects
* https://github.com/orgs/WordPress/repositories?q=openverse&type=all&language=&sort=
* https://seekseek.org/technology
* https://github.com/gigablast/open-source-search-engine
* https://github.com/benjojo/gophervista
* https://gitlab.com/clseibold/auragem_sis
* https://gitlab.com/clseibold/auragem_crawler
* https://github.com/elektito/gemplex
* https://github.com/acidus99/Kennedy
* https://github.com/marty1885/tlgs

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
