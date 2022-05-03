# JavaScript szerepe böngészéskor

## Bevezetés

* Sokan panaszkodnak azokra az oldalakra amik lassan töltenek be, illetve JavaScript nélkül csak tartalom nélküli oldalt jelenítenek meg.
* A kérdés, hogy lehet-e böngészni JavaScript nélkül vagy érdemes-e mérlegelni annak előnyeit.

## JavaScript tiltásának előnyei

### Személyes adatok védelme

* megnehezíti az adatszivárogtatást a meglátogatott oldalak vagy harmadik fél részére
  * böngésző ujjlenyomat (Tor), szupersütik és biometria, viszont enélkül sem lehetetlen
    * [passive-abuse-prevention.md](../server/passive-abuse-prevention.md#h%C3%A1l%C3%B3zati-ujjlenyomat)
* megnehezíti a komplex, rendszerszintű visszaéléseket (mind a meglévők mint az XSS, mind eddig fel nem fedezett esetekben)
* viszont JS nélkül is vigyázni kell: [en/article/remote-fingerprinting.md](../../en/article/remote-fingerprinting.md)

### Biztonsági szempontból

* Csökkenti a szoftverhibák kihasználhatóságának támadási felületet
* Megszünteti az architekturális információszivárgást (például a [spekulatív végrehajtás](https://en.wikipedia.org/wiki/Spectre_%28security_vulnerability%29) kapcsán)
* Jelentősen visszaszorítja az irányítási és jelentési csatornákat
* https://bleepingcomputer.com/news/security/google-pushes-emergency-chrome-update-to-fix-zero-day-used-in-attacks/ 2021
* https://bleepingcomputer.com/news/security/emergency-google-chrome-update-fixes-zero-day-used-in-attacks/ 2022
* https://googleprojectzero.blogspot.com/2021/01/in-wild-series-chrome-exploits.html 2017, 2019, 2020
* https://mytechdecisions.com/network-security/google-chrome-zero-days/ 2022
* https://www.zdnet.com/article/firefox-gets-fixes-for-two-zero-days-exploited-in-the-wild/ 2020
* https://bleepingcomputer.com/news/security/apple-fixes-ninth-zero-day-bug-exploited-in-the-wild-this-year/ 2021
* https://www.csa.gov.sg/singcert/Alerts/al-2022-010
* https://extremetech.com/computing/178587-firefox-is-still-the-least-secure-web-browser-falls-to-four-zero-day-exploits-at-pwn2own 2014
* https://ubuntu.com/security/notices/USN-4335-1 2020
* https://github.com/Escapingbug/awesome-browser-exploit
* https://github.com/tunz/js-vuln-db
* https://github.com/Metnew/uxss-db

### Nélkülözhetőség

A tapasztalat szerint 2021-ben a weboldalakon szereplő JavaScriptek nagy része nélkülözhető, vagy kényelmi funkciót lát el, vagy akár a felhasználói élmény szempontjából negatív.

#### Nélkülözhetőek elhagyásának hatékonysága

A felesleges JavaScript mellőzésének hatékonysága, tipikusan:

* Csökkenti a memóriaigényt
* Csökkenti a letöltendő adatmennyiséget ami gyorsítja a betöltést és még költségvonzatban is jelentkezhet
  * Lásd még: [../server/optimizing-web-proxy.md](../server/optimizing-web-proxy.md)
* Csökkenti a böngésző processzor terhelését és az ezzel kapcsolatos késleltetéseket és interakciózavarokat mind a parszolás, mind a tényleges futás következtében
  * https://en.wikipedia.org/wiki/Unobtrusive_JavaScript
* Előfordul, hogy néha JavaScript nélküli, sokkal takarékosabb változatra irányít a szerver (vélhetően keresőrobotok előnyben részesítése miatt)
* https://timkadlec.com/remembers/2019-01-31-putting-some-limits-on-javascript/
* https://timkadlec.com/remembers/2018-09-06-chromes-noscript-intervention/
* https://v8.dev/blog/cost-of-javascript-2019

### Hozzáférhetőség

Egyes weboldalak kevésbé hozzáférhetőek "progressive enhancement" hatására, azaz miután JavaScript alól gazdagabbá tették a navigációs felületet.
Ezen esetekben is segíthet a JavaScript teljes vagy részleges tiltása a gyakorlatban.

## JavaScript megoldások előnyei

### Kliens oldali feldolgozás

* A magunk által üzemeltethetőség népszerűsítését és ingyenes szolgáltatások fenntartható nyújtását elősegíti a szerver bonyolultságának és terhelésének csökkentése
* Megteremti a lehetőségét, hogy egyes titkokat ne juttassanak el a felhasználók (titkosítatlanul) a szerverre
* Speciális megoldásokkal kifejezetten csökkenthető a reakcióidő és/vagy az adatforgalom a gyakorlatban, de ezt 2021-ben csak elhanyagolható számú helyen alkalmazzák.
* https://css-tricks.com/should-a-website-work-without-javascript/

### Visszaélés elleni védelem

Lásd:

* [../server/passive-abuse-prevention.md](../server/passive-abuse-prevention.md)
* [../server/active-abuse-prevention.md](../server/active-abuse-prevention.md)

## Részleges JavaScript tiltás

Mivel ilyenkor nem a HTML `<noscript>` blokk érvényesül, így egyes weboldalak a szokványostól eltérően törhetnek el még akkor is, ha amúgy kínálnak JavaScript nélküli böngészőkre optimalizált változatot is.

### LibreJS

* https://www.fsf.org/campaigns/freejs _The Free JavaScript campaign_
  * https://www.gnu.org/philosophy/javascript-trap.html _The JavaScript Trap by Richard Stallman_
  * Ha szeretnénk azt támogatni, hogy 1-1 webszolgáltatás mind backend, mind frontend oldalon csak olyan kódot futtasson amit mi magunk is tudnánk üzemeltetni vagy akár módosítani
* Biztonsági szempontok (review)

### Reklámmentesítés

* Sokszor aránytalanul sokat lassít a tartalom megjelenítésén a reklámok _hatékonytalan_ betöltése, ezért azok eltüntetésének lehetnek jótékony mellékhatásai
* Előfordul kártevők fizetett reklámokon keresztül való terjesztése
* Ellenérv: veszélyezteti az ingyenes weboldalak és szolgáltatások fenntarthatóságát

### Kézi vezérlés

* Léteznek böngésző kiegészítések, melyek hivatkozáskor felajánlják az adott fájlok vagy kiszolgálók futtatásának tiltását (uMatrix, ScriptSafe)

## Kerülendő példák

### Enable-JavaScript

Egyes fejlesztők ahelyett, hogy a `<noscript>` részekbe alternatív tartalmat raknának a megnyithatóság érdekében azoknak akik letiltották a JavaScriptet, egy előre legyártott sablonszöveggel irányítanak egy olyan weboldalra ami elmagyarázza hogyan kell _bekapcsolni_ a JavaScriptet:

* https://enable-javascript.com/

## Statisztikák

Statisztikák adhatnak torzított becslést a fentiek miatt.

* https://stackoverflow.com/questions/9478737/browser-statistics-on-javascript-disabled
* https://gds.blog.gov.uk/2013/10/21/how-many-people-are-missing-out-on-javascript-enhancement/
* https://www.searchenginepeople.com/blog/stats-no-javascript.html
* https://softwareengineering.stackexchange.com/questions/26179/why-do-people-disable-javascript
* https://webmasters.stackexchange.com/questions/4733/should-i-worry-about-people-disabling-javascript
* https://webmasters.stackexchange.com/questions/1115/can-we-ignore-visitors-without-javascript-enabled
* https://softwareengineering.stackexchange.com/questions/25969/should-i-bother-to-develop-for-javascript-disabled
* https://ux.stackexchange.com/questions/15140/is-it-ok-to-require-certain-users-to-have-javascript-enabled
* https://softwareengineering.stackexchange.com/questions/23535/how-important-is-graceful-degradation-of-javascript
* http://www.punkchip.com/why-support-javascript-disabled/
* https://www.wired.com/2015/11/i-turned-off-javascript-for-a-whole-week-and-it-was-glorious/
