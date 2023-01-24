# Web cache archives

## Without JavaScript

### MementoWeb

* http://timetravel.mementoweb.org/memento/2023/https://en.m.wikipedia.org/wiki/Main_Page
* http://timetravel.mementoweb.org/list/20230101000000/https://en.m.wikipedia.org/wiki/Main_Page
* https://web.archive.org/web/en.m.wikipedia.org/wiki/Main_Page
* https://swap.stanford.edu/was/20230101000000mp_/http://en.m.wikipedia.org/wiki/Main_Page
* https://arquivo.pt/wayback/20230101000000mp_/https://en.m.wikipedia.org/wiki/Main_Page
* https://webarchive.loc.gov/all/20230101000000/https://en.m.wikipedia.org/wiki/Main_Page
* https://digital.library.yorku.ca/wayback/20230101000000/https://en.wikipedia.org/wiki/Main_Page
* https://haw.nsk.hr/wayback/20230101000000/http://en.m.wikipedia.org/wiki/Main_Page
* https://archive.ph/submit/?url=https://en.m.wikipedia.org/wiki/Main_Page
* https://wayback.archive-it.org/all/https://en.m.wikipedia.org/wiki/Main_Page
* https://wayback.nli.org.il/*/https://en.m.wikipedia.org/wiki/Main_Page
* https://haw.nsk.hr/wayback/*/https://en.m.wikipedia.org/wiki/Main_Page

### YaCy

* https://searchlab.eu/IndexBrowser_p.html?path=https://en.m.wikipedia.org/wiki/Main_Page

### Google

* https://webcache.googleusercontent.com/search?q=cache:https://en.m.wikipedia.org/wiki/Main_Page
* https://webcache.googleusercontent.com/search?q=cache:https://en.m.wikipedia.org/wiki/Main_Page&strip=1

### Proxy

* https://morty.searx.work/?mortyurl=https://en.m.wikipedia.org/wiki/Main_Page
* https://metager.org/

## Needs JavaScript

### Common Crawl

Can also be downloaded in bulk, but they also operate an index:

* https://index.commoncrawl.org/CC-MAIN-2022-49-index?url=https://en.m.wikipedia.org/wiki/Main_Page&limit=1&sort=reverse&output=json

```
curl \
  -r 270509538-$((19619+270509538-1)) \
  https://data.commoncrawl.org/\
crawl-data/CC-MAIN-2022-49/segments/1669446710941.43/warc/CC-MAIN-20221203212026-20221204002026-00046.warc.gz |
zcat
```

### Others

* http://www.bing.com/search?q=url:https://en.m.wikipedia.org/wiki/Main_Page
* http://search.yahoo.com/search?p=url:https://en.m.wikipedia.org/wiki/Main_Page
* http://baidu.com/search grep http://cache.baiducontent.com/

## References

* http://timetravel.mementoweb.org/about/#find
