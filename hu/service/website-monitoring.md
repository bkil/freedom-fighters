# Weboldal figyelés

## Cél

* Megelőző jellegű  cselekedetek a szerver hardveres egészségügyi állapotával kapcsolatban: hőmérséklet, rezonancia, fordulatszámok, teljesítmény mutatók, meghajtóprogramok naplóbejegyzései, [ECC](https://en.wikipedia.org/wiki/ECC_memory), [SMART](https://en.wikipedia.org/wiki/S.M.A.R.T.).
* Szeretnénk időben elhárítani amennyiben szoftveres vagy hálózati okokból belassul a szolgáltatásunk vagy elérhetetlenné válik egyes felhasználóknak.
* Terhelés utólagos elemzése, ez alapján a jövőbeli szoftveres vagy hálózati architektúra finomhangolása.

## Variációk

* publikus szolgáltatásra network monitoring: ping, TCP/IP fingerprinting, az alkalmazás réteg szerint HTTP/FTP/IMAP/stb lekérési próbálkozások, azok teljesítmény jellemzőik (késleltetés, átviteli sebesség, time to first byte)
* telepített ágenssel vagy ssh alapú belépéssel
  * általános rendszerinformációk
  * alkalmazás specifikus metrikák (BOINC termelékenység)

## Saját üzemeltetés

Hátránya, hogy a megfigyelt szerver(ek)en kívül rendelkezésünkre kell álljon egy független helyszínen biztosított monitoring szervernek is.

Alternatívaként amennyiben már eleve futtatunk több központból is szolgáltatásokat, akkor azon gépek segítségével figyeltethetnénk egymást is. Ehhez még a metrikák aggregálására is szükség lesz és gondoskodni kell a megfelelő vizualizációról is. Még ez sem tökéletes alternatíva ha nem csak az elérhetőségre vagyunk kíváncsiak, hanem más reprezentatívan mért teljesítménymutatókra is.

* https://en.wikipedia.org/wiki/Comparison_of_network_monitoring_systems
* https://en.wikipedia.org/wiki/System_monitor#List_of_software_monitors

Akár naplófájlok utólagos elemzéséhez:

* https://en.wikipedia.org/wiki/List_of_web_analytics_software#Free_/_Open_source_(FLOSS)

## Ingyenes szolgáltatók

Megjegyzés: magunk is futtathatunk hasonlót hardver nélkül amennyiben támogat cron időzített feladatokat egy [ingyenes dinamikus webtárhely](../free-paas-dynamic-web-hosting.md) szolgáltatónál.

* https://uptimerobot.com/
* https://www.montastic.com/
* https://www.statuscake.com/
* https://www.uptrends.com/free-website-monitoring
* https://betteruptime.com/
* https://www.freshworks.com/website-monitoring/
* https://site-monitoring.net/
* https://www.uptimerate.com/#price
* https://montools.com/
