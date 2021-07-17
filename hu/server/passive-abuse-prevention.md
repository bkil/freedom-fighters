# Transzparens támadás megelőzés

* Ezekkel az elemzésekkel a legtöbb esetben jóvá tudjuk hagyni a felhasználó hozzáférését anélkül, hogy neki cselekednie kellene.
* Sikertelenség esetén: [active-abuse-prevention.md](active-abuse-prevention.md).

## Hálózati védelem

DDOS felszívás

* CDN
* rate limiting: egy IP címről x másodpercenként y kérés jöhet be
  * esetleg HMAC tokennel a kliensnél tartani az állapotot vagy a hálózati késleltetésre is építeni
  * normál forgalom alapján megjegyezni a CGNAT-okat (egész település, ISP, kollégium)
  * ASN vagy GeoIP ország alapján szabályok
* Szándékosan egyre lassabban küldeni a választ vagy annak első bájtjait amennyiben tudjuk erre optimalizálni a szerverünket
* támadás érzékelés
  * összterhelés változás
  * hibakód változás
  * variáns korreláció (paraméterek, sütik, azonosítók, ujjlenyomat)
  * ASN vagy GeoIP-re lebontva változás
* túlterhelés esetén agresszíven gyorsítótárazott, minimalizált, statikus változatot kiszolgálni az oldalból
* Tiltólista gyűjtögetés
  * `robots.txt`-ben letiltott és láthatatlan linken elérhető csapdák

### Hálózati ujjlenyomat

* User-Agent és egyéb HTTP kérés fejlécek asztali és mobil böngészőkön leggyakrabban megfigyelhető kombinációi
* GeoIP, reverse DNS és traceroute: kiszűrni a proxy, IaaS és PaaS címeket (DNSBL?)
* Késleltetés és hopszám mérése
* https://en.wikipedia.org/wiki/TCP/IP_stack_fingerprinting
  * TCP dugóelhárító algoritmus, ablakméret, opciók, csomagvesztés kezelése, TLS jellemzők
  * szekvencia és időbélyegző lötyögésé és sebessége alapján követés

## Szürkezóna

Csoportokba soroljuk attól függően, hogy pontosan milyen feltételeket teljesített a felhasználó:

* Tesztelő
  * Bizonyos dolgok csak olvashatóak vagy a névleges korlátnál kisebb kapacitásúak
  * Csevegőben: tilos a közvetlen üzenet és megemlítés, csak publikus szobában tud írni
  * Bármilyen jelzésre azonnal némítás, visszavonás az eset elemzéséig
    * "`Bejelentés`" gomb az üzenetei mellett
    * "`Helyeslés`" gomb reputáció építéshez
    * Szigorú nyelvi szűrések
    * Heurisztikus szabályok
    * Megbízható felhasználók viselkedésének statisztikáihoz hasonlítani
* Újonc
    * "`Bejelentés`" gomb az üzenetei mellett
* Megbízható

## Oldal hozzáférési nehezítések JavaScript nélkül

* Opcionális: valami egyedi hibaoldal keretében (401?) visszaadni a tartalmat
* Opcionális: szerver oldali scriptekkel egy új megnyitáskor egy hibaoldalt visszaadni (4xx/5xx?) amiben emberi nyelven meg van fogalmazva, hogy be kell nyomni a frissítés gombot és utána hibakód nélkül visszaadja a tartalmat
* Opcionális: folyamatkijelzés mellett nagyon lassan streamelni az oldalt, időtúllépésben bízva (31 másodperc?)
* Opcionális: hivatkozzunk a fejben egy `.css`-re és csak azután adjuk vissza a tartalmat iframe-ben miután lekérik a hivatkozást
* Opcionális: meta-refresh várakoztatás után kérje le és adja vissza az igazi tartalmat
  * Inspiráció: A botok csak bizonyos ideig futtatják az oldalt és utána vesznek egy DOM snapshotot
  * Valószínűleg a jobb botok a refresh URI-t is le fogják crawlolni
  * Generáljunk véletlenszerű vagy aláírt refresh cél URI-t ami csak bizonyos időablakban és IP címről adjon vissza tartalmat: így amennyiben egy késleltetett crawl sorba kerül a lekérés, már ne legyen érvényes a link
  * Állítsunk be sütit is és ezt is ellenőrizzük

## JavaScript oldal hozzáférési nehezítések

* Opcionális: JavaScript futtatása juttasson a szerverhez kliens ujjlenyomatot a válasz megtekintése előtt
* Opcionális: JavaScript számítási kapacitás, memória vagy tárhely rendelkezésre bocsátása (proof of work), bár újabban ehhez hozzájárulás szükséges
* Opcionális: JavaScript várakoztatás után kérje le vagy adja vissza a tartalmat
  * Inspiráció: a botok csak bizonyos ideig futtatják a scripteket és utána vesznek egy DOM snapshotot
* Opcionális: JavaScript reklám betöltése után jelenjen meg a tartalom
* Opcionális: JavaScript (vagy CSS) alapú biometria
* Opcionális: (Turing-teljes) JavaScript futtatása jelenítse meg a tartalmat
