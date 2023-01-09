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

## Ethical

### Qwant

* https://lite.qwant.com/
* FR
* also uses Bing
* can be used without JavaScript

### Mojeek

* https://mojeek.com/
* GB
* can be used without JavaScript

### MetaGer

* http://metager.de/
* DE
* uses various other providers under the hood
* returns results within an iframe - opening the link directly allows viewing the results without JavaScript
* https://github.com/bkil/static-wonders.js/blob/master/userjs/metager.de.user.js

### Marginalia

* https://search.marginalia.nu/
* FOSS, can also be self-hosted
* https://git.marginalia.nu/marginalia/marginalia.nu
* can be used without JavaScript

## Worrisome

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

### DuckDuckGo

* https://lite.duckduckgo.com/lite/
* USA
* uses Bing and Yandex under the hood
* can be used without JavaScript

### Startpage

* http://startpage.com/
* NL
* owned by adtech company System1
* forwards your search to Google
* formerly: lxquick
* prescribes the use of JavaScript, but results are actually visible with the following CSS addition:

```
.layout-web__body .show-results {
  visibility: initial;
}
```

### Monopolists

## FOSS

* https://en.wikipedia.org/wiki/Yacy
* https://domainsproject.org/
* https://github.com/tb0hdan/domains

## Own crawler

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

## Image search

* https://en.wikipedia.org/wiki/Reverse_image_search#Application_in_popular_search_systems
* https://en.wikipedia.org/wiki/List_of_CBIR_engines
* https://en.wikipedia.org/wiki/Content-based_image_retrieval#Techniques
