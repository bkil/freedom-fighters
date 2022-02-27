# Email címeink és aliasok

## Alapok

### Cél

Olyan formában tesszük megjeleníthetővé a címünket:

- hogy azt a jelenleg elterjedt böngészők meg tudják jeleníteni, ideálisan kattintható formában, ideálisan akadálymentesen
- ideálisan QR kódban is ábrázolható amire a mobilon tudunk kattintani
- erre a címre az elterjedt webmail, mobil és asztali levelezőkliensek tudjanak levelet feladni
- ide az elterjedt postafiók szolgáltatók tudjanak levelet kézbesíteni
- itt az általunk megválasztott (de elterjedten elérhető) postafiók szolgáltatás be tudja fogadni a levelet meghatározható változatlansági fok mellett

### Elvek

Minél több szabványt és RFC implementációt kellene helyesen implementálniuk egymásra rétegezve az elérési lánchoz, annál nagyobb az esély hogy valamelyiket elrontják. Lásd:

- [email-address-syntax.md](email-address-syntax.md)
- [email-address-syntax-proprietary.md](email-address-syntax-proprietary.md)

Feltételezzük, hogy a kéretlen levélküldők fejlesztői nem az élvonalból kikerült szoftverfejlesztők és/vagy az általuk vásárolt eszközök olcsók. Proaktívan keressünk hibákat az algoritmusaikban, hogy törekedjünk azok megkerülésére.

### Védelmi lánc

Ami ellen nem védekezhetünk maradéktalanul:

- Ha valaki embereket bérel fel, hogy rendszeresen látogassák a weboldalunkat, kimásolják az email címünket amire kézzel feladja a levelet vagy bemásolják a spamot a kapcsolati űrlapunkba
- Ha valaki végigolvassa ezt a dokumentumot és a benne foglalt összes tanácsot kijátssza
- https://www.rhyolite.com/anti-spam/you-might-be.html

### A címet tartalmazó oldal védelme

- [passive-abuse-prevention.md](passive-abuse-prevention.md)
- [active-abuse-prevention.md](active-abuse-prevention.md)

## Általános nehezítések

- A tartalom ábrázolásának trükkjei: _(... lásd lenti védelmi módszerek fejezet)_
  - https://en.wikipedia.org/wiki/Address_munging
  - https://en.wikipedia.org/wiki/Disposable_email_address#Using_%22sub-addressing%22
  - Legalább egy nagybetűt, pontot és ha az támogatott, subaddressinget is tartalmazzon a localpart és az e nélküli címre érkező leveleket blokkoljuk: egyes címlista tisztítók próbálnak kanonikus formára hozni
    - Sajnos például a Mailman is kisbetűsít, így regisztrációnként ellenőrizendő
  - A végső címzettnél vagy többszörös korrelált címzetteknél érdemes a fióknevet olyanra választani amit egyes címtisztítók kiszűrnek (`^(test|example|spam|noreply|no-reply)@|@(test|example|spam)\.`)
- `robots.txt`-ben letiltott és láthatatlan linken elérhető spamtrap és tarpit
- Opcionális: kapcsolati űrlapon lehessen írni nekünk amit szerver oldalon továbbítunk - szintén le kell védeni, de más módszerekkel (CAPTCHA)


### Küldési nehezítések

- Az oldalról megszerzett címünkre ne tudjanak üzenetet küldeni
- Az MTA-nk nehezítse meg a kézbesítést
  - https://en.wikipedia.org/wiki/Greylisting_(email)
  - https://en.wikipedia.org/wiki/Nolisting
  - https://en.wikipedia.org/wiki/Anti-spam_techniques
  - https://en.wikipedia.org/wiki/Anti-spam_techniques_(users)
  - https://en.wikipedia.org/wiki/Email-address_harvesting#Countermeasures
  - https://en.wikipedia.org/wiki/Challenge%E2%80%93response_spam_filtering
  - https://en.wikipedia.org/wiki/Tagged_Message_Delivery_Agent
  - http://www.junkemailfilter.com/spam/how_it_works.html
  - https://cwiki.apache.org/confluence/display/spamassassin/OtherTricks#
  - Alternatívaként bizonyos címlista tisztítók eldobnak egy címet ha nincs MX record a domain alatt (pedig ilyenkor a szabvány szerint ugyanúgy kézbesítenek, csak az A vagy AAAA rekord alapján)
  - Amennyiben lehetséges és mi üzemeltetjük az NS-t, azon a szinten is rakhatunk be hálózati ujjlenyomat ellenőrzést és blocklistet (+GeoIP és többszörös címzettek közti korreláció)
- Meg tudjuk különböztetni attól, mintha egy legitim böngészőben kattintana és utána MUA-n keresztül küldene levelet
- MTA szinten futtatható, kézzel írt, közösségileg fenntartott általános spam szűrő
- MTA azonnal `reject`-elje a gyanús, de nem teljesen kamu leveleket, hogy arra küldéskor eljusson egy `bounce` a feladóhoz
- MTA véletlenszerű ideig karanténban tartás, valós idejű közösségi spam szűrés
  - Eleinte csak a célszemélyek egy részének majd fokozatosan egyre többnek kézbesítjük, akik olvassák, és remélhetőleg bejelenti még mielőtt a többieknek is kézbesítődne
- Opcionális: MTA tanítható spam szűrő

### MTA szűrés

- Előtte törekedjünk a GnuPG aláírás, DMARC, DKIM vagy ARC-seal ellenőrzésére
  - levlistánál először gyakori szabályok alapján, majd brute force a végét csonkítva próbáljuk megjavítani a hash-et
    - Mailman például külön MIME csatolmányban fűzi a levelünkhöz a levlista aláírást
- Engedjük át:
  - Amelyik feladónak már írtunk (vagy kézzel felvettük) és akivel hitelesíthetően levelezünk
  - Aki olyan címünkre ír ami az engedélyezőlistán szerepel
  - Az olyan levelet ami a lent részletezett nehezített `mailto:` feltételrendszert kielégíti
- Ha spamtrap címünkre írnak:
  - Frissítsük a spamszűrőt
  - Járuljunk hozzá a közösségi szűrőhöz
- Ha spamot kapunk:
  - Dobjuk el a levelet
  - Ha nem tartós cím, kezdeményezzük a címünk cseréjét
    - Új cím generálása, felvétel az engedélyezőlistára
    - A régi címhez kapcsolt regisztrált szolgáltatásnál címcsere
    - Tartósságtól függően azonnal vagy egy idő után vegyük le a régit az engedélyező listáról
- Dobjunk el minden mást

## Védelmi módszerek

### Nem alkalmazandó

Akivel korábban kapcsolatba léptünk:

- Akivel hitelesíthetően levelezünk (GnuPG aláírás, DMARC, DKIM)
- Egyébként egyedi címet kell generálnunk részükre
  - ideiglenesen átirányítható
  - kis entrópiájú
  - szintaxisban nem nehezített

### Gyakran cserélhető

- Weboldalunkon kattintható `mailto:` URI scraper spam bot elleni védelemmel
- Weblapunkon szövegesen email cím scraper spam bot elleni védelemmel
- Szolgáltatás regisztrációhoz - papír vagy online
- levlista feliratkozás és válaszlevelekben (`Reply-To` vagy `From`)

### Ideiglenesen átirányítandó

- Névjegykártyánkon szövegesen vagy QR kód amit ember felvisz marketing adatbázisba
- Mindegyik egyedi legyen, hogy egyenként lehessen tiltani (esetleg elévíteni egy idő után)

### Tartósan átirányítandó

- A spamszűrő súlyozásának testreszabása érdekében ezeket egyedien generáljuk ki minden egyes előfordulásnál
- Nyomtatott publikációnkban
  - Minden módosításnál egyedi cím
- Levelezőlistán hozzászólóként
  - Akár olyan címet is adhatunk ami minden levelet eldob ami nem a levlistáról jön
- Levélben beküldött módosításcsomag küldőjeként és végén a `signed-off-by`
  - Levelenként (vagy időszakonként) egyedi cím
- git committer, git author
  - Projektenként egyedi cím

## Címünk változtatása

- Legyen elég entrópia benne
  - Kanonikus verziót alapból blokkoljuk
  - Cserélhetőség
- Ha kiszivárog (marketing továbbértékesítés vagy kártevők révén), a szokatlan szintaxis segíthet megbújni a spammerek adatbázistisztítási folyamatában

## Címünk publikásása

### SVG

- foreignObject -> data URI -> HTML

### CSS

- `content` illetve más kevésbé akadálymentes, vizuális körüljárás
- ez inkább csak a megjelenített változatnál használható

### HTML form

- Az `action` lehet `mailto:` link is

### Közösségi szűrők

- Regexpeket és más szabályok wikiben (giten) közösen naprakészen tartva amivel kanonizálható vagy felismerhető a spam

### Spamtrap hamis címek

Helyezzünk a HTML különféle láthatatlan részeire spamtrap címeket is olyan formában ahogy a lehető legtöbb arató begyűjtheti:

- HTML megjegyzések `<!-- ... -- ... -- -->`
- CDATA
- script
- style
- noscript
- Láthatatlan: színek, betűméret
- CSS: átlapolás, hover, animáció
- Eldöntendő, hogy pont ugyanúgy kódolva mint az igazit vagy kicsit egyszerűbben

Új feladótól érkező levél megjelenítése előtt 12 óra karantén, ha esetleg addig érkezne egy spamtrap címünkre is hasonló példány akkor eldobjuk mindkettőt.

### HTML sortörések

### HTML szóközök

### Mezők összekapcsolása

Adjunk meg több címet is: `to`, `cc` és `bcc`.
Eldobjuk amennyiben nem minden címre küldték ki közel azonos időpillanatban azonos tartalommal (például mert szétvágták begyűjtéskor).

#### Nem kézbesíthető másolatok

- A megadott redundáns címek közül lehet olyan is ami szándékosan nem lesz kézbesíthető például annak szintaxisa miatt, de a másolat készítésének ténye megjelenik a sikeresen kézbesített példány fejlécben.
- Van amelyik szolgáltató eldobja a kapcsolatot ha egyszerre valaki 1-2-nél több kézbesíthetetlen levelet próbál feladni ugyanabban a kötegben
- Egyes MUA és MTA visszautasíthatja a levelünket amennyiben abban bizonyos típusú szintaxishiba szerepel.

### Változatlan tárgy

Eldobjuk ha nem a megadott tárggyal küldték (`subject`).

### Törzsben változatlan szövegrész

Eldobjuk ha hiányzik a törzsből (tipikusan a végéről) az előre megadott aláírás

### Címek elnevezése

- Régebbi szabványban használatos volt, tehát ezt is kezelniük kell: `"John Smith" <a@example.com>`.
- Ez sokrétű jelet és ékezetes karaktert elbír, praktikus mindent felsorolni amink csak van úgy, hogy a lehető legtöbb vágót megzavarja: `"@>.\\&%+\" <"` stb.

### Címek fiókneve

Sarokesetek:

- Ékezetek: ajánlás, de nem minden program kezeli (régi Thunderbird), így nem javasolt
- UTF8mb4
- Idézőjel nélkül beírható ritka jelek
  - A pluszjel (`+`) a `mailto:` percentile encoding miatt is jó sarokeset (hibásan ábrázolt szóköz)
  - Egyes speciálisan kezelt karakterek többszörös előfordulása is jó (<a+b+c@example.com>)
  - Plusz a végén: `a+@example.com`
- Idézőjelezett forma: kötetlenebb jelkészlet és szintaxis
- Aláhúzás (`_`) vagy kötőjel (`-`) az elején
- Több kötőjel egymás mellett
- Egyes MTA kártevővédelem miatt visszautasítja ha van benne függőleges vonás (`|`)
- Egyetlen karakter, számjegy
- Új, hosszú TLD

Egységesítés:

- Sok szolgáltatónál egyenértékű: kis-nagybetűk
- Van szolgáltató ahol egyenértékű:
  - beékelt pontok
  - beékelt kötőjelek
  - beékelt visszaperjelek (`\\`)
  - plusz, százalék vagy kötőjel karakter utáni rész
    - ezeket izgalmas kombinálva és többszörösen alkalmazni

### Szándékos fióknév hibák

- Több plusz egymás mellett (`a++b@example.com`): jónak számít, de a Gmail például nem kezeli

### Címek doménje

- Szögletes zárójelezett IPv4 és IPv6 numerikus literális forma: sajnos van aki nem támogatja
- Ékezetek akár egy aldoménben
- UTF8mb4 aldomén
- Több kötőjel (`a-b-c.example.com`)
- Számjegy a gépnév elején: mostanában általában bejegyezhető, de régen nem volt gyakori
- Többszörös aldomén, ideálisan minél hosszabb beágyazással (`a.b.c.d.e.f.g.h.i.j.example.com`)

### Szándékos domén hibák

- Kötőjel egy komponens elején-végén: sajnos sok validátor megfogja
- Több kötőjel egymás mellett: hibás példaként
- Rossz TLD (számjegy, nem létező kombináció): _-**TODO** valamelyik MUA megfogja?_
- UTF8mb4 TLD
- Egyetlen karakter: hibás példaként
- Aláhúzás, akár az elején, akár egyetlen aldomén (`@_.example.com`)

### HTML entity escaping

- `&#37;` = `%`
- `&#X2e;` = `.`

### HTML percentile encoding

- `%40` = `@`

### MIME encoding

- A törzset leszámítva mindenhol alkalmazható, például `subject`-ben is
- Akár szavanként lehet váltogatni
- `_` = ` `

#### Quoted printable

- `=3d` = `=`

#### Base64 printable

- RFC4648 javaslata szerint a CRLF figyelmen kívül hagyható

### Kis-nagybetű váltakoztatása

### Tömöríthető szóközök

- Strukturált mezőknél

### Folding

Sorok megtörhetők új sorral ha a következő szóközzel kezdődik. Ez a törzsben gyakori, máshol szokatlan lehet, tehát izgalmas.

## Kérdések

- Milyen email címet tudunk létrehozni nagy szereplőknél?
- Milyen email címet tudunk létrehozni tipikus doménhez vagy ingyen tárhelyhez tartozó email szolgáltatásoknál?
- Milyen email címre tudunk levelet küldeni melyik nagy szereplőtől?
- Milyen alternatív email címekre küldött levelek érkeznek meg ugyanabba a postafiókunkba?
- Reply-To

## Nehéz példák

Előremutatóan ha SourceHut git tárolóba szeretnénk változtatáscsomagot beküldeni, a megadott email cím tartalmaz hullámjelet és perjelet is, úgy mint: `~ownername/projectname@lists.sr.ht`

## Támadók

### Címlista tisztítás

- https://github.com/deajan/linuxscripts/blob/master/emailCheck.sh#L64
  - kisbetűsít, behelyettesít elgépelt és ritka domén neveket, ellenőrzi, hogy van-e MX rekord
