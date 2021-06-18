# Optimalizáló web proxy

## Koncepció

* mobiltelefonos és laptopos böngészéshez
* gyorsabb oldalbetöltés
* adatforgalom megtakarítás
* akkumulátor megtakarítás: kevesebb rádióhasználat, kevésbé terhelő megjelenítés
* mobilneten vagy lassú és szakadozó ingyen wifin
* ideálisan minden család magának üzemeltetné akár VPS-en, akár otthoni korlátlan neten

## Kivitelezés

* a megtakarítások egy része a mobil eszközön futtatott lokális proxyval magában is elérhető
  * laptop esetén szinte triviális ugyanazt a kódot futtatni mint a távoli szerveren, bár Androidon sem lehetetlen körüljárni
* a megtakarítások egy része böngésző kiegészítővel is kiváltható lenne: nem minden eszközre elérhető vagy macerás mindenhol egyenként telepíteni
* a megtakarítások egy részéhez böngésző fork szükséges (vagy egy második lokális proxy ami a távoli proxyval egyedi protokollon kommunikál): nem minden eszközre elérhető vagy macerás mindenhol egyenként telepíteni
* a megtakarítások egy része csak egy távoli szerveren megvalósítható vagy azzal jelentősen javul

## Szolgáltatások

### Távoli proxy szolgáltatások

* HTTP/2
* link prefetching
* elmaradt minifikáció pótlása
  * betűtípusok csonkítása
* képek .WebP újratömörítése
  * minőségének rontása: akár adaptívan felismerni a rossz formátumban mentett fotót vs. rajzot és poszterizál vagy veszteségessé tesz
* mozgó gif minőségrontása vagy WebM újratömörítése
* videó transzkódolás
* xz vagy jobb tömörítés a helyi proxyval
* CSS inlining + tree shaking (kattintásra visszavonható)
* túl sok fejlesztést igényelne: a legnagyobb megtakarításhoz egy igazi böngészőmotort kellene futtatni pár másodpercig és utána eseményekkel szinkronban kommunikálni Opera Mini mintájára

### Távoli vagy helyi proxy szolgáltatások

* kozmetikai és tranzitíven lekövetett tartalomszűrés, sokszor külső hivatkozásokat is meg tud takarítani

### Helyi proxy szolgáltatások

* SSL közbeékelés (man in the middle)
  * lehetne olyan beállítás amivel változatlanul hagyná a HTML (JavaScript, CSS) fájlokat és integritásukat garantálná az eredeti tanúsítvány és módosított TLS lekérés segítségével
* gyorsítótárazhatósági javítások
* gyűjtögető gyorsítótárazás
  * adott lemezterület előre feltöltése népszerű vagy látogatott oldalakkal
  * `zsync` vagy `rsync` frissítés: a lokális proxy a távoli proxy-tól a saját gyorsítótárában szereplő változathoz képest csak a változásokat kéri le a HTML, CSS, JS dokumentumokból, fontokból vagy akár más weboldalak alapján, ehhez nagy segítség lehet ha minél szélesebb körű tartalmakkal eleve fel van töltve a gyorsítótár
* oldalak vagy tartalmak megjelölése, hogy azok kerüljenek később letöltésre amikor rendelkezésre fog állni szélessávú kapcsolat

### Távoli proxy nélkül hasznos helyi proxy szolgáltatások

* gzip helyett brotli kényszerítése HTTPS nélkül is
* fájl magic és fejlécek alapján adaptív HTTP range request hívásokkal részleges letöltés
  * Néha kivonatolható a mozgó gif előnézeti képe, fotók előnézete (progressive JPEG)

### Távoli proxy nélkül hasznos böngésző szolgáltatások

* fájl magic és fejlécek alapján adaptív HTTP range request hívásokkal részleges letöltés
  * Nagy képeknél lehet, hogy jobb híján egyfajta véletlenszerű bejárás hasznosabb betöltési folyamatkijelzést biztosítana (vagy eleje, vége, közepe, többi rész)
    * JPEG blokkonként független
    * PNG esetén a hosszak és literálisok alapján lehet, hogy lenne valami nézhető és korreláció alapján kijönne az eltolás is
  * PDF és más dokumentumnál az éppen megtekintett oldalak szerint, további fejlesztésekkel analóg módon PDF optimalizálás, mert sokszor át lehet ugrani a túl nagy képbeágyazásokat ha valaki csak a szövegre kíváncsi
  * CSS, JavaScript, betűtípusok részei igény szerint letöltve
  * Véletlenszerűen vagy priorizálva ha tudjuk, hogy főleg merrefelé szoktak lenni a változó vagy az érdekesebb részek oldalspecifikusan, és vagy automatikusan vagy kérésre le is állíthatjuk a letöltést miután megvan a tartalom

### Böngésző vagy helyi proxy szolgáltatások

* túl nagy képek betöltése kattintatás után (főleg távoli proxy nélkül hasznos), esetleg betöltés közben kattintásra megszakítás
* videók blokkolása, legkisebb minőségűre kényszerítése, előre letöltés csökkentése
* betűtípusok blokkolása
* olyan `User-Agent` feltüntetése aminek hatására kisebb változatot adnak vissza oldalak
* osztott könyvtár hivatkozások kicserélése egységesre ami jobban gyorsítótárazható
* heurisztikus optimalizációk (kattintásra visszavonhatóak ha elrontják a megjelenést)
  * JavaScript (CSS) blokkolás, majd kattintásra csökkenő valószínűségi sorrendben egyesével visszaengedélyezés amíg a kívánt tartalom meg nem jelenik

## Példák

* https://wiki.mozilla.org/Mobile/Janus
  * https://blog.browsernative.com/mozilla-janus-firefox-data-compression-391/
  * https://github.com/mozilla/node-janus
  * https://github.com/mozilla/janus-addon
* https://en.wikipedia.org/wiki/Opera_Mini
  * https://www.ghacks.net/2011/04/14/opera-turbo-overview-discovering-opera-part-1/
* https://en.wikipedia.org/wiki/UC_Browser
* https://www.ghacks.net/2019/04/24/google-deprecates-chrome-data-saver-extension-for-the-desktop/
  * https://blog.browsernative.com/data-compression-feature-of-chrome-mobile-175/
* https://www.groovypost.com/howto/amazon-kindle-fire-silk-browser-disable-cloud-page-accelerator/
* https://en.wikipedia.org/wiki/Puffin_Browser
