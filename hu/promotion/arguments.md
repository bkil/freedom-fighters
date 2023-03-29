# Érvek népszerűsítésnél

## Miért használjunk OpenStreetMapet

## Miért használjunk szabad szoftvereket

* Bárki számára szabadon (ingyenesen) elérhető.
* A korábbi egyszeri licencvásárlás helyett, egyre több szoftvergyártó vezeti be az előfizetéses modellt, amelynél évente szükséges megvásárolni az új verzió használati jogát. (pl Office365, megfelelő vírusirtó). Ez egy átlagos család esetében jelentősen megterhelheti  a költségvetést. Tört szoftverek használta illegális és nem is ajánlott , mert a keygen-ek és crack-ek nagy valószínűséggel vírusokat, kémprogramokat tartalmaznak. "Freeware" programok használata szintén nem ajánlott, mert legtöbbször hirdetéseket tartalmaznak és biztonsági kockázatot is jelentenek.
* Ezzel szemben a szabad szoftverek kódja bárki számára megismerhető. A  szoftverek megbízhatóságát maga a közösség ellenőrzi. Használatuk biztonságos.
  * Több szem - többet lát: https://en.wikipedia.org/wiki/Linus%27s_law
* Nagy választék áll rendelkezésre jó minőségű ingyenes szabad szoftverekből. Ne programokhoz ragaszkodjunk, hanem feladatokhoz keressünk  megfelelő eszközöket, programokat (fájltömörítő, webböngésző, videólejátszó, fájlkezelő, stb).  Itt keresgélhetünk https://alternativeto.net/
* A közösségi tulajdon gyarapítását támogatjuk vele.
* A legtöbb nyílt forrású program Windowsra és Linuxra is elérhető. Így szabadon megválaszthatjuk milyen operációs rendszert használunk. 

## Asztali Linux használatának előnyei

* Könnyen biztonságossá tehető
* A nyílt forrás és széles körű használat miatt könnyen megbizonyosodhatunk a biztonságáról
  * Megismerhetjük, hogy mikor mit csinál vagy akár javíthatunk is rajta
* Léteznek ingyenes változatok is
* Választható szintű terméktámogatás
* Biztonságos lehetőségek távfelügyelethez és távsegítséghez - csak az nézhet bele a gépünkbe akit mi akarunk
* Régi gépen is jól mehet
  * Könnyen gyorsítható
* Megfelelő szaktudással nagyfokú testre szabhatóság (csomagok, configok, patchek, 3rd party alternatívák)
* Segítségnyújtásnál jól bevált recepteket lehet automatizálni is, vagy akár magában a rendszerben javítani (felületet, detekciókat, hibakezelést), míg Win esetében rengeteg hibalehetőséggel járó manuális kattintgatás szükséges
* Akinek kell kötegelt feldolgozás, arra léteznek Linuxon jól bevált eszközkészletek
* Fejlesztőknél az LXC (docker, stb.) egy nagyon hasznos funkció, amely segíti a napi munkavégzést. Más operációs rendszeren ez csak virtuális géppel megy. Macen még több falba ütközik: 1000 alatti portokkal nem megy a Docker

### Linux plakátötletek

* "A legjobb védelem az óvszer után a pingvin. Mutatjuk miért"

## Linux használata elleni kifogások

### Előtelepítés

* Kevés az elérhető notebook/PC a piacon ami Linuxszal van telepítve

### Teljes törlés

* Jelenleg ez az üzenet: töröld le a működő OS-t, vele az összes adatodat, és telepíts egy másikat! Ebből a „töröld” és a „telepíts” a két nagyon erős és nagyon ijesztő szó

### XP használók

* Nincs pénze új gépre
* Nincs pénze új Windowsra
* Nagyon megszokta (hasonló külalakú Linux megfelelhet)
  * Iskolában is az van
* Régi szoftvert használ ami nem fut új Windowson (vagy weboldalt amihez olyan plugin/applet kell amit sehol máshol nem támogatnak)

### Windows használók

* Nem tud az alternatíva létezéséről
* Csak Windows-t támogató programok (pl. MS Access, egyedi programok), játékok
  * Iskola vagy munkahelyi feladathoz kötődően szeretne gyakorolni otthon is
  * Egyes népszerű játékok, pl. ...
    * Viszont sokat segít ez ellen: https://en.wikipedia.org/wiki/Steam_(service)
* Jó lesz neki mert ő úgyis csak böngészget (erre a Linux is jó lenne)
* Új hardverek támogatása
* Az átállás pénzbe és időbe kerül

### Korábbi átállási tanulságok

* https://www.linuxjournal.com/content/german-open-source-experiment-things-not-going-plan
* Hardver támogatás (szkennerek, nyomtatók)
* Interoperabilitás
* Tanfolyamok
* Elfogadottság a felhasználók által

## Szabad közösségi és kommunikációs szolgáltatások előnyei

Úgy általában is minden jó szándék mellett egy fokkal kockázatosabbnak számítanak a centrálisan milliárd ember által használt alternatívák szemben a peer to peer, vagy self-hosted decentralizáltakkal. Ellenben néhány nagy piaci szereplőnkről különféle okokból egyéb aggályok is bizonyításra kerültek a múltban (ezen kívül van amit még nem tudtunk bizonyítani).

Facebook, Slack, Skype és egyéb zárt online szolgáltatások nyílt alternatíváinak az előnyei:

### Nyílt szabványú protokoll

* Számtalan különféle kliens létezik és/vagy létrehozható hozzá
  * Felhasználói felület jobban testre szabható
  * Létezhet sávszélesség optimalizált változat is ami takarékoskodik a mobilnettel
  * Létezhet offline is használható változat (pl. secure scuttlebutt)
* Testre szabható, programozható szűrések a különféle nem kívánatos tartalmak és/vagy emberek ellen
* Szabadon fejleszthetők appok, nem cenzúrázzák

### Központi cenzúra

* Nem feltétlenül létezik központi cenzúra

### Hacker hozam

* Decentralizáció miatt kevesebb incentíva a hacker támadásokra: kevesebb nyereség per szerver

### Kódújrahasználás

Több újrafelhasználás a világban és több review miatt több esély van a biztonságos programozásra

* https://en.wikipedia.org/wiki/Linus%27s_law

### Felhő konfigurálási tévedések

Mivel olyan nagy felhőkben mint az Amazon százával vannak az igénybe vehető szolgáltatások, sokkal több lehetőség van elhibázni a hálózatot mind a beállítások, mind infrastruktúra programozás oldalról

Sebezhetőségek:

* https://arstechnica.com/information-technology/2020/10/white-hat-hackers-who-had-control-of-internal-apple-network-get-288000-reward/
* https://www.foxbusiness.com/features/why-hackers-love-the-cloud
* https://thehackernews.com/2016/08/dropbox-data-breach.html
* https://www.zdnet.com/article/hostinger-resets-customer-passwords-after-security-incident/
* https://nki.gov.hu/it-biztonsag/hirek/tobb-millio-szallodavendeg-adata-szivargott-ki/
* https://news.cornell.edu/stories/2016/05/shortened-urls-may-open-window-your-life
* https://www.bleepingcomputer.com/news/security/capcom-hit-by-ragnar-locker-ransomware-1tb-allegedly-stolen/amp/

### Párhuzamos monetizációs modellek

* Föderált hálózatoknál párhuzamosan életképesek az alternatív szerver monetizációs modellek
* pl. Diasporában az egyik résztvevő havidíjas, másik reklámokat néz, harmadik a személyes adataival és szokásaival fizet, negyedek közösségi munkával és mind tudja egymást követni

### Nem módosíthatják önkényesen az ÁSZF-et

* network effect miatt magához láncolják a felhasználót és kapcsolatait
* Pontosan tudjuk, hogy a szerver mit csinál az adatainkkal

### Monetizációs struktúra átláthatósága

* Minél kisebb egy cég annál átláthatóbb a monetizációs struktúrája, piaci mérlege, motivációi
* Kis szervert akár otthon is üzemeltethetünk (Raspberry Pi 4), IPv6 előnyben, NAT megkerülési megoldások
* Tesztelendő? https://yggdrasil-network.github.io/

### Nincs beetetés

* Ha később árat emel vagy zavaróbb helyeken helyezi el a reklámokat
* Ha nekünk kellő funkcionalitásokat redukál (például FB weboldal régen mobilon is ment, ma már nem)

### Fenntarthatóság

* bárki tudja tovább üzemeltetni ha az eredeti üzemeltetőnek már nem éri meg vagy csődbe megy
* Csak megbízható üzemeltetőt válasszunk: ismerettségi körünkből, hatóságok, nemzetközi szervezetek, korábbi előtörténete avagy "priusza", transzparencia, incentívák avagy motivációk
* Végpontok közötti titkosítás előnyben, mert ilyenkor a szerver üzemeltetőben sem kell megbízni

### Nem tartják fogságban az adatainkat

* szintén az ÁSZF és technikai megoldások segítségével bármikor dönthetnek arról, hogy kik érhetik el a tartalmainkat és hogyan, ez akár ránk is vonatkozik
* Például eleinte nem volt regisztráció köteles a tartalom olvasása, utána felbukkanó ablakkal ösztönöztek rá, akár be is vezethetik később, hogy csak regisztrációval lehet a kulcs tartalmakat olvasni

### Választás szabadsága

* A közösségi hálónk részére biztosítjuk a választás szabadságát, nem kényszerítjük rájuk (ÁSZF, monetizációs modell, bizalom, SLA, cenzúra, adatkezelés)

### Webes változat

* Ugyanúgy létezik webes változat is amikor minden adatunk a felhőben megvan ha bármi történne a készülékkel
* be lehet állítani távoli backupolást a végpontok közötti titkosítást használó alternatíváknál is

Sebezhetőségek:

* https://www.forbes.com/sites/zakdoffman/2020/03/04/microsoft-nightmare-login-hack-this-new-video-shows-how-your-password-can-now-be-stolen/

## Zárt közösségi és kommunikációs szolgáltatásokon maradók kifogásai

Facebook, Skype-on maradó felhasználói tábor kifogásai és azok lehetséges körüljárása:

### Network effect

* Minden ismerősöm már itt van, kedvenc márkám csak itt van
  * _-> Nincs igazi megoldás, de át kell hozni őket, illetve átmeneti időszakban mind a kettőn fent lehet lenni_
* Van bejáratott és kiépített márkám (brandem), marketing hálózatom, közösségem, sokat fizettem érte, nem akarom csak úgy ott hagyni, újra ki kéne építenem
  * _-> Nincs igazi megoldás, de enyhíthető: ingyenes szerver, keresztlinkelés, keresztmarketing_
* Single sign-on authentication (központi azonosítás) rengeteg külsős webhelyre ("lépjen be vagy regisztráljon Facebook-kal")
  * _-> Létezik más OpenID alternatíva is_
* Több ismerősöm ért hozzá ha segítséget kell kérni
  * _-> Online segítségnyújtási lehetőség köré közösség építése és népszerűsítése: fórum, csevegőszoba, wiki, használati útmutató, képernyő megosztás, oktató videók_

### Megszokás

* _-> Létezhet megjelenítési téma (kinézet, arculat) ami emlékeztet a korábbi alternatívára (vigyázva a jogi védelmekre)_
* _-> Betanulást segítő játékos programok_

### Érdektelenség

> nincs takargatni valóm
> nincs kedvem

* _-> Figyelemfelhívás, oktatás, népszerűsítés_

### Nehéz váltani és fél tőle mert bonyolult

> Nekem ez magas

* Nem ismer alternatívákat
  * _-> népszerűsítés_
* Tanácstalanság: a bőség zavarában nem tudja, hogy melyik alternatívát válassza (Diaspora, Friendica, Mastodon, Pleroma, Misskey stb)
  * _-> népszerűsítés, integráció, SSO_

### Kedvenc alkalmazások

> A kedvenc appom hiányzik

* _-> Sokat ki tudunk fejleszteni ezek közül_

### SLA

* Az SLA (rendelkezésre állás) szerverenként eltérő így lehetnek néha lassulások ha ugyanazt a díjmenteset használják korlátlanul sokan
* _-> Létezik a kiválasztást ez alapján segítő táblázat, azt kapja az ember amiért fizet_

### Üzletpolitikai kedvezmények

* az adott napon az adott mobilnet szolgáltató "zero rated" tarifát alkalmaz: például korlátlan FB videókat lehet rajta nézni, vagy COVID alatt ingyen oktatási felhasználás
* Hátrány: időszakosság, bármikor meggondolhatják magukat
* _-> Ha eléri egy alternatíva egy adott részesedést egy adott területen, esélyesen ott is felajánlhatnánk hasonlót egy idő elteltével (pl. 5-10%?)_

### Magyar fordítás

* _-> lefordítjuk ami hiányzik_

### Szülői felügyelet

* Valamelyik zárt alternatívánál létezik szülői felügyeletű regisztráció
* _-> Implementálhatjuk_

## Zárt, központosított videómegosztó platform hátrányai

Szürke, nem skálázódó segédeszközök.

Videók lementése a Youtube-ról amikhez szerzői jogi szempontból volna engedélyünk, a ToS szempontjából valamelyest aggályos:

* https://en.wikipedia.org/wiki/Youtube-dl

Youtube-dl alapú webszolgáltatás üzemeltetéséhez

* https://github.com/Tzahi12345/YoutubeDL-Material

## Átállás kockázatai

### Ügyfélkör

* Nem lesz elég (fizetőképes) kereslet
* Túl sokan lemorzsolódnak, viszik a projekt rossz hírét

### Versenytársak

* Akadályokat gördítenek elénk
* Elkezdik ledolgozni egyes hátrányaikat

## Referenciák

Egy szabad self-hosting szerver részletes threat modellje:

* https://freedombone.net/threatmodel.html

Továbbiak:

* https://www.stallman.org/stallman-computing.html
* https://www.gnu.org/philosophy/javascript-trap.html
* https://www.gnu.org/philosophy/who-does-that-server-really-serve.html
