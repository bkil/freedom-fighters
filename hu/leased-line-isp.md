# Publikus szolgáltatások üzemeltetésére alkalmas internet előfizetés

## TLDR

* Nem szabad otthoni interneten publikus szolgáltatásokat üzemeltetni.
* Ezt egy akár otthon, akár szerverközpontban kialakított bérelt vonalon szabad megtenni (pl. VPS, lásd [cheap-server-hosting.md](cheap-server-hosting.md))

## Háttér

Mind a belföldi globális internet összeköttetés, mind a nemzetközi adatkicserélési pontok jelentős költséggel épültek ki és kerülnek üzemeltetésre. A 90-es években jelentősen növelte az internet elterjedését az az üzleti gyakorlat, mi szerint az előfizetőknek nem dedikált erőforrásokat osztanak ki, hanem azokat masszív csoportokba összefogva statisztikai alapon azzal számolnak, hogy adott időpillanatban mindenki csak a lehetséges maximum elhanyagolhatóan kis részét fogja kihasználni. Ez az arány 1:10 és 1:100 között szokott lenni.

* https://en.wikipedia.org/wiki/Overselling#Communications_access_networks_(last-mile)
* https://en.wikipedia.org/wiki/Peering
* https://en.wikipedia.org/wiki/Border_Gateway_Protocol
* https://en.wikipedia.org/wiki/Autonomous_system_(Internet)
* https://en.wikipedia.org/wiki/Administrative_distance
* https://en.wikipedia.org/wiki/Internet_exchange_point
* https://en.wikipedia.org/wiki/Internet_backbone#Economy_of_the_backbone
* https://en.wikipedia.org/wiki/Backhaul_(telecommunications)
* https://en.wikipedia.org/wiki/Upstream_(networking)
* https://en.wikipedia.org/wiki/Middle_mile
* https://en.wikipedia.org/wiki/Average_per-bit_delivery_cost

Ez már csak azért is szükségszerű, mivel a népsűrűség alacsony szintje miatt racionálisan nem szőhetünk át egy egész város minden utcáját terabites kapcsolatokkal azért, hogy minden háztartás tudjon szerver üzemeltetni amin akár a teljes sávot is kitolhatja. Ennél sokkal ésszerűbb és hatékonyabb ha a kicserélő központok vannak kapacitással átszőve és oda magas sűrűséggel és felügyelettel helyeznek el szervereket az üzemeltetők.

## Cél

Célunk olyan, szabad szoftveres publikus szolgáltatások üzemeltetése, amivel versenyezhetünk a kevésbé etikus monopol szereplőkkel, illetve aminek segítségével közösségeket szolgálhatunk ki, köthetünk össze.

## Korlátok

Amennyiben (ideális esetben) céljainkhoz az otthoni felhasználók el nem hanyagolható  része csatlakozna, az jelentősen aláásná az internet szolgáltatók üzleti modelljét. Emiatt mindegyik szolgáltató már eleve tisztán megfogalmazza azt az ÁSZF-ben, hogy nem támogatja ezeket a tevékenységeket.

Amelyik kisebb szolgáltató esetleg a mai napon nem tartalmaz jogilag érvényesíthető  megfogalmazást erre vonatkozólag, borítékolható, hogy amint ez kimutathatóvá válik a monitoring rendszereikben, ÁSZF módosítással fognak élni, tehát felesleges csak emiatt bújni a dokumentumokat.

### Elfogadható használat

Az ÁSZF nyelvezete alapján a szolgáltató üzletpolitikájával összeegyeztethető amennyiben a szolgáltatást az előfizető felelősségére és irányításával a háztartás szükségleteire használják.

Ebbe életszerűen beleérthető:

* A háztartás lakói a háztartás IoT eszközeire, munkaállomásra távmunkára vagy biztonsági mentés ügyén visszacsatlakoznak kívülről.
* A háztartás lakói egymással kommunikálnak a hálózaton keresztül.
* A háztartást látogató vendégek is csatlakozhatnak a hálózathoz a látogatásuk idejére közös elfoglaltság keretében. A vezeték nélküli vendéghálózat létrehozását a szolgáltató eszközei is fel szokták ajánlani alapfunkcióként.

### El nem fogadható használat

Életszerűen nem fenntartható példák:

* Nagy forgalmú, korlátozás nélkül, publikusan elérhető szervert üzemeltetünk egész nap.
* Internet kávézót üzemeltetünk otthon: ellentételezésért cserébe biztosítjuk a használatot.
* A szomszédok lemondják a saját internet előfizetésüket, hogy a miénket használják a saját háztartásukból.

## Szerver igényeink

Olyanokra lehet gondolni, mint egy dokumentumfelhő, videómegosztó, közösségi háló vagy csevegőplatform.

Az otthoni előfizetésekre egyrészt nem akarnak elég magas SLA-t vállalni, másrészt pedig jelentős költségnövekedéshez vezet a maximális kihasznált sávszélesség és a nemzetközi gráfon történő fan-out növekedése.

### Szerver benne foglalt

Tipikusan szoktak díjmentesen biztosítani email és PHP web tárhelyet még otthoni előfizetés mellé is amivel a felmerülő publikus elérhetőségi igényeket kielégítik. Erre sokféle PHP alapú hobbi szolgáltatás telepíthető, akár egy Friendica is.

### Szerver lehetséges szolgáltatói egyezmény

Etikailag elképzelhető, hogy akadna olyan szolgáltató aki egyedi írásos szerződés alapján adott portokon keresztül adott sávszélesség hányadot rendelkezésünkre bocsátana amennyiben ez garantáltan elhanyagolható terhelést okoz és PR érdekeket szolgál. Például publikus Friendica példány üzemeltetése engedélyezett 2Mb/s-ig 1Gb/s előfizetésen. Sajnos PeerTube-ra ez túl kevés volna.

### Szerver VPS

Egy igazi megoldás erre ha bérelünk egy olcsó VPS-t erre a célra:

* [cheap-server-hosting.md](cheap-server-hosting.md)

## Kliens igényeink

A hátrányos helyzetűek kommunikációs képességeinek megteremtése.

Sajnos már a legkisebb mértékű  megosztás is alkalmas lehet arra, hogy az esetek el nem hanyagolható részében lemondják a szomszédok az előfizetésüket, mondjuk 1Gb/s-ből 1Mb/s is elég kommunikációra, vagy 5Mb/s már alap videózáshoz is.

Külön nehezítő tényező, amennyiben a szolgáltató érdekelt a mobil telekommunikációs hálózatokban is. Ekkor közvetlen érdekellentétet képvisel ha harmadik fél számára elérhetővé válik rajtunk keresztül az ingyenes VoIP vagy üzenetküldés. Ez 2021-ben már fennáll minden nagy szereplő esetén: Telekom, Vodafone (UPC), Digi (Invitel) és Telenor (mifi).

Azt gondolhatnánk, hogy ez kevésbé aggályos akkor, ha olyan mobilnetet osztunk meg ami alacsony benne foglalt adatkerettel rendelkezik. Viszont vegyük figyelembe, hogy ezen adatkeretek árazása úgy lett kialakítva, hogy a felhasználók azok jelentős részét nem használják ki egyéni szinten. Szintén áremelkedéshez vezetne ha nőne a kihasználtság.

### Kliens lehetséges szolgáltatói egyezmény

Etikailag elképzelhető, hogy akadna olyan szolgáltató aki egyedi írásos szerződés alapján a drágább csomagjaihoz korlátozott mértékű  "összesített közösségi sávszélességet" biztosítana amin a külsősök osztozhatnának (1Gb/s mellé web+email 1Mb/s csúcs, 0.5Mb/s folyamatos?).

Reálisabb alternatívaként lehetne regisztráltatni a felhasználókat és rendelkezésre állna egy olyan mértékű személyhez kötött napi-havi adatátviteli korlát, ami kellően differenciálná a szolgáltatást egy saját igazi otthoni előfizetéstől (1GB/hó?).

### Kliens caching web proxy

Elvileg ÁSZF szempontjából nem támadható az a megoldás, ha valaki a háztartása részére üzemeltet egy hálózaton belüli caching web proxy-t (például hogy ne töltse le minden gép ugyanazt a frissítést külön-külön). Ekkor a háztartási gyorsítótár adattartama az eredeti weboldalak szerzői jogi védelme alá esnek. Ezt szem előtt tartva ennek a gyorsítótárnak a továbbosztása nem esik már az internetszolgáltatónk érdekkörébe, tehát akár harmadik fél számára is továbbadható.

Ez nagyjából azt jelenti, hogy etikus, de szürke területként harmadik személy használhatja a caching web proxy eszközünket passzív módban, azaz oly módon, hogy a harmadik személy ne tudja befolyásolni, hogy a proxy milyen kéréseket továbbít az internet felé, ennek következményeként nem generálhat az internet szolgáltató által megfigyelhető forgalmat, tehát többlet terhelést sem.

### Kliens biorobotok

Egy nem skálázható, de jogilag érvelhető érdekes körüljárás még, hogyha otthoni előfizetők önkéntes "biorobotként" töltenek le weboldalakat rászoruló harmadik felek kérésére. Ekkor az adott szolgáltatás használója az adott otthoni előfizető lesz, így nem áll fenn a megosztás tényállása.

Amennyiben ez a folyamat teljes mértékben automatizálásra kerülne, így az otthoni előfizető személyes közreműködése már nem volna szükséges, a **használat** jogi tényállása már a harmadik félre állna fenn, amit viszont az ÁSZF tilt.

### Kliens független hálózaton

Persze a legtisztább megoldásként bármikor kiépíthetnénk egy az internettől teljesen függetlenített [mesh networking](https://en.wikipedia.org/wiki/Mesh_networking)/[delay-tolerant networking](https://en.wikipedia.org/wiki/Delay-tolerant_networking) kommunikációs hálózatot, de ehhez egy sor új alkalmazásra volna szükség illetve további véleményformálásra.

## IXP példák

* https://deninet.hu/szerver-hosting
  * 17900 Ft/hó + ÁFA: 1Gb/s szerver elhelyezés (átlagos 100Mb/s, garantált: 80Mb/s BIX, 30Mb/s külföld)

## Példák bérelt vonalakra

Sajnos üzleti okokból csak nagyon ritkán publikus az árjegyzék és valószínűleg alkuképes is a szándéktól és konkrét helyszíntől függően. Pont a nagyobb, feltételezhetően olcsóbb szolgáltatóktól nincsenek adataink, de nagyságrendi becslés az alábbiak alapján is tehető:

* keresőszó https://duckduckgo.com/?q=site%3Ahu+b%C3%A9relt+vonali+internet+forint
* https://3ctelecom.hu/szolgaltat/mikrohullamu-internetszolgaltatas (36 hó hűség)
  * 9 ezer Ft/hó: 10/10 Mb/s * 25%, 98.5% SLA
  * 12 ezer Ft/hó: 10/10 Mb/s * 100%, 99.5% SLA
  * 100 ezer Ft/hó: 150/150 Mb/s
* https://www.internet-x.hu/szolgaltatasok/internet/berelt-vonali-szimmetrikus-internet-szolgaltatasok/
  * 40 ezer Ft/hó: 20/20 Mb/s
* http://tranzittelekom.hu/szolgaltatasok-bereltvonal.php
  * 70 ezer Ft/hó: 20/20 Mb/s, 2 év
* https://www.bix.hu/dokumentumok/bix_dijak
  * nettó 120 ezer Ft/év alapdíj + 30 ezer Ft/hó 1Gb/s port + 30 ezer Ft/hó 2U Co-Location
  * Ez azért ennyire "olcsó", mert ehhez be kell költözni hozzájuk és/vagy onnan kihúzni saját magunknak kábelt vagy vezeték nélkül jelismétlőket a célterületünkre, amihez karónként és kábelcsatornánként a helyi önkormányzatok is elvárnak engedélyt és havidíjat illetve kizárólagosság esetén az NMHH frekvenciahasználati koncessziót

Már ebből is látszik, hogy nem véletlenül kerül 5 ezerbe az otthoni gigabites internet a városban - ha ezt elkezdenék az emberek kihasználni, 100x annyiért kéne adni.

## Példák tovább nem osztható bérelt vonalra

Kínálnak vállalatoknak olyan csomagokat ahol szerver üzemeltetése már megengedett, bár itt alapból szintén tiltják a hálózati szolgáltatás nyújtását és továbbértékesítést. Elképzelhető, hogy egyedi ajánlat keretében ők is engedélyezhetik.

* http://www.wla.hu/Araink/4/
  * 14500 Ft/hó: 8/8 Mb/s
* https://last-mile.hu/internet_corporate.html
  * 19500 Ft/hó: 25/8 Mb/s garantált, 2 év hűség, fix IP
* http://net-portal.hu/szolgaltatasok/mikro-internet/
  * 40 ezer Ft/hó: 5/5 Mb/s
