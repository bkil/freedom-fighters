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
  * beleértve az inline változatokat
* opcionálisan a (nagyobb) inline erőforrások törlése vagy külső hivatkozásra cserélése, hogy annak letöltése kliens oldalon választható legyen
  * JavaScript, CSS, CSS háttérkép, SVG, iframe, tetszőleges egyéb data uri
* mozgó gif minőségrontása vagy WebM újratömörítése
* videó transzkódolás
* xz vagy jobb tömörítésű kapcsolat a helyi proxyval
* CSS inlining + tree shaking (kattintásra visszavonható)
* túl sok fejlesztést igényelne: a legnagyobb megtakarításhoz egy igazi böngészőmotort kellene futtatni pár másodpercig és utána eseményekkel szinkronban kommunikálni Opera Mini mintájára

### Távoli vagy helyi proxy szolgáltatások

* kozmetikai és tranzitíven lekövetett tartalomszűrés, sokszor külső hivatkozásokat is meg tud takarítani

### Helyi proxy szolgáltatások

* gyűjtögető gyorsítótárazás
  * adott lemezterület előre feltöltése népszerű vagy látogatott oldalakkal
  * `zsync` vagy `rsync` frissítés: a lokális proxy a távoli proxy-tól a saját gyorsítótárában szereplő változathoz képest csak a változásokat kéri le a HTML, CSS, JS dokumentumokból, fontokból vagy akár más weboldalak alapján, ehhez nagy segítség lehet ha minél szélesebb körű tartalmakkal eleve fel van töltve a gyorsítótár

### Távoli proxy nélkül is hasznos helyi proxy szolgáltatások

* SSL közbeékelés (man in the middle)
  * lehetne olyan beállítás amivel változatlanul hagyná a HTML (JavaScript, CSS) fájlokat és integritásukat garantálná az eredeti tanúsítvány és módosított TLS lekérés segítségével
* oldalak vagy tartalmak megjelölése, hogy azok kerüljenek később letöltésre amikor rendelkezésre fog állni szélessávú kapcsolat
* gyorsítótárazhatósági javítások
  * heurisztikák: beágyazási hely, fájlnév, Content-Type vagy magic alapú fájltípus
  * a válaszban küldött elévülési idők kiterjesztése
  * a válaszból kimaradt elévülési idők és etag pótlása
  * a kérésben kényszerített újratöltés felülvizsgálata
  * az elévült dokumentum etag vagy dátum alapú frissítése a forrástól
  * opcionálisan a frissítés megszakítása ha a forrás a metaadatok alapján hibásan gyorsítótárazik (Content-Length, Last-Modified, ETag, Instance Digest, metalink mirrors, Content-MD5 stb)
    * https://datatracker.ietf.org/doc/html/rfc6249#section-6 _Metalink/HTTP: Mirrors and Hashes_
    * https://datatracker.ietf.org/doc/html/rfc3230#section-4.3.2 _Instance Digests in HTTP_
    * https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.15 _HTTP/1.1 Header Field Definitions_
    * https://www.ietf.org/rfc/rfc1864.txt _The Content-MD5 Header Field_
  * máshol is megtalálható osztott erőforrások kicserélése hálózati szinten
    * amennyiben fájlnév és hívási környezet alapján vélelmezhető, hogy máshonnan is elérhető, a webszerver szoftver ismeretében lekéréskor próbálhatnánk `If-None-Match` fejléceket generálni (ha nem kell az i-node, csak a dátum és a méret), különben `HEAD` alapján előre ellenőrizni, esetleg különleges esetekben még az `If-Modified-Since` (`If-Unmodified-Since`?) is szóba jöhet
    * amennyiben az egyezés ki nem zárható és az adott fájl tartalmában (ideálisan elején) kimutatható egyedi azonosításra alkalmas rész (például HTML authoring metaadatok, könyvtárverzió, git hash, dátum és idő, CRC32, bejegyzésszámláló, stb) akkor azt is figyelembe véve mérlegelni a behelyettesíthetőséget
  * adott fájlok struktúrájának vagy változástörténetének ismerete szerint céltudatos ofszettel frissíteni, majd szintetizálni az új változatot
    * RSS feed: ha az elejére kerülnek az új bejegyzések és adott számú bejegyzés van benne, annak elég csak elejét olvasni a végét pedig eldobni, méret alapján visszaellenőrizni
    * honlap: sok egyszerűbb hír- és hirdetőoldalon csak a reklám változik, az időjárás, névnap, utolsó frissítés dátuma, ezen kívül az új bejegyzések a HTML tetejére kerülnek
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
  * Matrix Element Web
    * hangulatjelek és vezérlők helyett nagyobb Unicode karakterek (tud is ilyet betöltési hiba esetén)
    * 1-1 eseményobjektumról el lehetne dönteni, hogy a blurhash, előnézeti vagy teljes változatot jelenítsük meg - néha az előnézeti több helyet foglal mint az eredeti vagy más formátumban van (jobban lekérdezhető részlegesen)
* videók blokkolása, legkisebb minőségűre kényszerítése, előre letöltés csökkentése
* betűtípusok blokkolása
* favicon blokkolása vagy cseréje egy másik, gyorsítótárazott képre
* manifest blokkolása
* HTTP kérés fejléceiből a redundáns mezők kitörlése (tulajdonságok, referer, felesleges sütik)
  * Ideálisan a Vary fejléceket is a gyorsítótárazásért
* CDN-eken (is) megtalálható osztott erőforrás hivatkozások (JavaScript, CSS, fontok) kicserélése egységesre ami jobban gyorsítótárazható
  * https://www.w3.org/TR/SRI/ _Subresource Integrity (SRI) hash digest_
  * http://microformats.org/wiki/hash-examples#Existing_Practices "Link Fingerprints"
* takarékos üzemmódban az előrelátóan történő letöltések tiltása
* heurisztikus optimalizációk (kattintásra visszavonhatóak ha elrontják a megjelenést)
  * képek betöltésre kattintásra, addig a helyükön elérési út alapján számolt színek és/vagy formák
    * igény esetén lehetőség navigációs ikonok tömeges betöltésére
  * JavaScript (CSS) blokkolás, majd kattintásra csökkenő valószínűségi sorrendben egyesével visszaengedélyezés amíg a kívánt tartalom meg nem jelenik
  * helyileg kiszolgált osztott erőforrás hivatkozások kicserélése CDN-re amennyiben beágyazási hely, fájlnév és esetleg fájlméret alapján máshol is elérhető
* párhuzamos letöltéseknél a nem-kritikus erőforrások depriorizálása beágyazási hely, származás, fájlnév, Content-Length, Content-Type vagy magic alapú fájltípus szerint
  * ha rugalmas vagy módosítható a böngésző: `<head>`-ből kritikus függések kimozdítása és a tartalmazó dokumentum priorizálása, különben a `<head>` utáni rész depriorizálása
  * éppen csak annyira visszalassítani, hogy ne szakadjon meg a kapcsolat: adott időközönként továbbítani csomagokat, illetve egyes szerverek korlátozzák egy lekérés teljes idejét (például 30 másodperc)
  * adott domain, aldomainek, külső hosztok
  * HTML, navigációs ikonok, CSS, JavaScript, fotók
* Az eredeti forrástól takarékosabb változat lekérése
  * weboldalak asztali változatának átirányítása mobil vagy WAP változatra
  * wiki forrásának lekérése és abból helyi weboldal formázás (akár fele-harmadakkora, és még ebből is sokszor range request levághatná fejléceket)
    * https://en.wikipedia.org/w/api.php?action=parse&prop=wikitext&format=json&page=Wikipedia
    * https://en.wikipedia.org/wiki/Special:Export/Wikipedia
  * olyan `User-Agent` feltüntetése aminek hatására kisebb változatot adnak vissza oldalak például keresőmotorok részére
  * főoldal meglátogatása előtt felajánlani az RSS/Atom feed megjelenését vagy keresést a portálon

## Példák

* https://wiki.mozilla.org/Mobile/Janus
  * https://blog.browsernative.com/mozilla-janus-firefox-data-compression-391/
  * https://github.com/mozilla/node-janus
  * https://github.com/mozilla/janus-addon
* https://github.com/asciimoo/morty
* https://en.wikipedia.org/wiki/Opera_Mini
  * https://www.ghacks.net/2011/04/14/opera-turbo-overview-discovering-opera-part-1/
* https://en.wikipedia.org/wiki/UC_Browser
* https://www.ghacks.net/2019/04/24/google-deprecates-chrome-data-saver-extension-for-the-desktop/
  * https://blog.browsernative.com/data-compression-feature-of-chrome-mobile-175/
* https://www.groovypost.com/howto/amazon-kindle-fire-silk-browser-disable-cloud-page-accelerator/
  * https://en.wikipedia.org/wiki/Amazon_Silk#Architecture
* https://en.wikipedia.org/wiki/Puffin_Browser
* https://en.wikipedia.org/wiki/MarioNet_split_web_browser#Proof_of_concept
* https://en.wikipedia.org/wiki/Bolt_(web_browser)#Server-assisted_data_compression
* https://en..wikipedia.org/wiki/Skweezer
* https://en.wikipedia.org/wiki/Vision_Mobile_Browser
