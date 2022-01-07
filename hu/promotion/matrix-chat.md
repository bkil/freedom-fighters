# Mátrix népszerűsítés

## Bevezetők

* https://wordsmith.social/matrix-magyarul/matrix-kezdoknek
* https://blogg.grin.hu/2021/01/114-matrix_a_decentralizalt_nyilt_kommunikacios_platform_hasznalata/
* https://video.ploud.fr/search?languageOneOf=hu&tagsAllOf=Matrix&sort=-match&searchTarget=local

## Angol bevezetők

* https://noordstar.me/b/how-to-join-matrix.md Element, FluffyChat, matrixcli, Miitrix

## Hogyan lehetne népszerűsíteni a Matrixot

@notramo felvetése.

* UX tapasztalatok gyűjtése
  * Matrix projekt szárnyai alatt, random embereket megkérdezni, hogy kipróbálnának-e egy titkosított, biztonságos, közösségileg fejlesztett chat appot (Element) egy hivatalos önkéntes tesztelési projekt keretein belül.
  * El kéne magyarázni 1 (max. 2) percben, hogy miért jobb ez az app, és, ha lenne kedvük, akkor
    * minden kérdésüket felírni (ami az app használatára vonatkozik, így a nem egyértelmű részeket lehetne javítani)
    * ha nem működik valami, felírni
    * a felhasználó pár mondatos visszajelzését felírni az app benyomásáról
  * Statisztikát levonni, és egyeztetni a Matrix dev csapattal a javításról.
* A4-es méretű, olcsón nyomtatható plakát készítés?
  * A digitális csatornákon áramló nagy mennyiségű infó miatt az emberek kevésbé fogékonyak.
  * Kereskedelmi platformokon search bubbling van, ezért nem minden réteg látja, az utcán viszont mindenféle emberek járkálnak.
  * Mindenképp egyeztetni a Matrix HQ-val.
  * Grafikai design!!!
  * Esetleg adott szobákat hirdetni valahogy?
* Regisztráció nélküli azonnali használat
  * SMS alapú regisztráció, ami a telefonszámot használja az authentikációhoz, hasonlóan, mint Signal, Telegram, Google Duo
  * Ha a sok SMS költségét nem tudnák állni, lehetne ezt a funkciót fizetőssé tenni, mégpedig, hogy a felhasználók küldik az SMS-t egy regisztrációs kulcssal, amit a szervertől kapnak interneten (ehhez minden országban kéne egy szám, mert a roaming drága)
  * P2P Matrix lenne a legjobb megoldás, mert ott még SMS sem kell, de az még sehol nem tart
* Regisztrációs flow gyorsítása
  * Eszköz-közti hitelesítés egyszerűsítése
  * Key backupot nem erőltetni, hanem, ha több eszköz van belépve, automatikusan gossipolni kilépéskor a kulcsokat

## Mátrix plakátötletek

* Megszólítás
  * "Informatikában jártas vagy?"
  * "Telepíts etikus csevegőprogramot ismerőseidnek!"
  * "Telepítettél már életedben programot? Akkor ez sem okozhat gondot."
  * "Ennél a csevegőprogramnál tuti rosszabbat használsz"
  * "Ez a csevegőprogram a barátod - miért nem teszed fel a barátaidnak is?"
  * "Melyiket választod, a kéket vagy a pirosat? Válaszd inkább a Mátrixot!"
  * "Egy trendi csevegőprogram azoknak akik nem félnek a telefonjuktól és gépüktől"
  * "Ha ezt felteszed, okosabb lehetsz mint az eszközöd"
  * "Csetelj szabadon a Mátrixon - soroljuk az előnyeit"
  * "Messenger, WhatsApp, Snapchat, Viber és Skype - miért ne használjuk?"
  * "5 titok az üzenetküldő alkalmazásodról"
* Kiemelendő megkülönböztető jellemzők
  * self-hostable, föderált
  * Szabad szoftver
  * Számtalan kliens alkalmazás elérhető kinek-kinek szája íze szerint
  * Egyéni vagy csoportos videótelefonálás
  * Nyílt szabvány, REST API - számtalan automatizáció, integráció, bot, bridge elérhető
  * Szobákba épülő widgetek, osztott jegyzetek, dashboardok
* Egyéb jellemzők
  * Publikus szobákban kívülről üzenetekre hivatkozhatóság
  * Gazdag üzenetformázás (Markdown), emoji, reactji, idézés, válaszüzenet
  * Olvasottságjelzés
  * Fájlküldés
  * Csoportos beszélgetések eszközeink között szinkronizált csevegéstörténettel
  * (titkosítás: javítandó)

## Mátrix homeszerverek

* https://austinhuang.me/matrix-homeservers.html
* https://github.com/ara4n/matrixservers#matrix-server-list
* https://glowers.club/wiki/doku.php?id=wiki:newfriends#what_homeserver_should_i_use
* https://hello-matrix.net/public_servers.php
* https://matrix.grin.hu/rooms/
* https://publiclist.anchel.nl/
* https://the-federation.info/matrix%7Csynapse
* https://wiki.asra.gr/en:public_servers
* https://joinmatrix.org/servers/
  * https://github.com/austinhuang0131/joinmatrix/
* https://fediverse.blog/~/FossMessenger/matrix-server
* TODO: joinmatrix.rocks = homeservers.mx
