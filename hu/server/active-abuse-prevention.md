# Aktív támadás megelőzés

* Ha a passzív ellenőrzés nem volt eredményes:
  * [passive-abuse-prevention.md](passive-abuse-prevention.md)

## Bizalom horgonyzás

Adott, általunk megbízhatónak tartott támadáselhárítást biztosító külső entitásnál már bizonyított személy

### Ajánlás

* Meglévő felhasználónk által korlátozott számban küldhető meghívó
* Közzétett információk alapján meglévő felhasználóink általi megszavazás
* Ha utólag kiderül, hogy egy ajánlás rossz volt, elévülő negatív visszacsatolása (reputáció, jogvesztés, további ellenőriztetés)
* web of trust: GnuPG kulcsaláírás vagy más hasonló módon következtethető, hogy van legalább adott számú ismerőse a rendszerünkben akik univerzálisan kezeskednek a valódiságukért

### Áttételes

* Gyakorlatilag bármit kérhetnénk amire sokan regisztráltak a lehetséges felhasználóink közül
  * osszon meg egy adott bejegyzést a Wordpress.com-on vagy más központi közösségi hálójában
  * írjon valamit a közreműködéssel rendelkező Wikipédia, BOINC, Wigle, stb profiljára
  * utána adja meg nekünk a linkjét
* email megerősítés
  * email fogadással: abban szereplő linkre kattintás vagy kód bemásolása a weboldalunkon
  * fordított e-mail validáció: a felhasználó küldene megerősítő emailt, amin keresztül szintén gazdag hálózati ujjlenyomat állna rendelkezésre

### SSO

Nagy, közismert szereplőknél tett regisztráció igazolására:

* OpenID
* OAUTH 2.0
* OpenStreetMap ID
* GitHub, GitLab, BitBucket
* közösségi hálók: Facebook, Twitter

### Személyazonosító okmányhoz kötött

* Bankkártyán kis összeget zároltatni majd azonnal visszaadni
* Bankszámláról kis összeget utaltatni majd azonnal visszaadni
* A felhasználó bankszámlájára kis összeget utalni
* SMS vagy DTMF telefonos azonosítás
* Elektronikus aláírás megbízható harmadik fél által tanúsított kulccsal (pl. e-személyivel)

### Token alapú

* https://privacypass.github.io/ Ha egyszer megoldottunk valamennyi feladványt, annak igazolását névtelenül fel tudjuk használni különféle weboldalakon

## Ellentételezés alapú

Célunk, hogy vagy ne érje meg a támadónak nagy számban végrehajtani a visszaélést, vagy hogy a vele nekünk okozott közvetlen többletköltséget fedezze.

* A legtöbb gyakorlati támadást már egy elenyészően alacsony ellentételezés is megakadályoz a skálázásban, pl. $1 egyszeri díj
* Egy nagyobb összeget is letétbe (kaucióba) helyeztethetünk vagy zároltathatunk ami csak a felmondást követő adott idő elteltével (1-7 nap) akkor jár vissza, ha nem történt visszaélés
  * Arányosnak kell lennie a várhatóan okozható kárral vagy eszmei értékkel. Például ha egy felhasználónk a fórumra spamot küld amit egy moderátor utána kitöröl azzal kisebb kár ér, mintha valaki megszerez egy email címet amire utána akár hosszútávon kéretlen levelek tömegét küldheti.
* Esetleg barter, például ossza meg adománykérésünket a legalább adott szintet elérő közösségi hálójában

## Proof of work

* http://webcomputing.iit.bme.hu/
* https://distri.js.org/
* https://joseconstela.github.io/acio-js/
* https://github.com/sedflix/SadlyDistributed

## CAPTCHA

### Alternatív CAPTCHA áttekintések

Korábban bennük is felmerültek alternatívák:

* https://github.com/vector-im/riot-web/issues/3606
* https://github.com/matrix-org/matrix-doc/issues/1281
* https://github.com/zeratax/matrix-registration
* https://codeberg.org/Codeberg-Infrastructure/CaptchaService#user-content-other-solutions
* https://switching.software/replace/google-recaptcha/
* https://gitlab.com/gitlab-org/gitlab-foss/-/issues/45684

### FOSS CAPTCHA

* https://www.phpcaptcha.org/try-securimage/
* https://github.com/subwindow/negative-captcha
* https://www.mtcaptcha.com/#mtcaptcha-demo
* https://hackint.org/transport/tor#Anonymous_Account_Registration
* https://www.w3.org/WAI/GL/wiki/Captcha_Alternatives_and_thoughts
* https://captcheck.netsyms.com/
  * Piktogramok közt kell választani
  * https://source.netsyms.com/Netsyms/Captcheck
* https://github.com/desirepath41/visualCaptcha
  * Piktogramok közt kell választani
  * Példa: https://demo.visualcaptcha.net/
* https://www.solvemedia.com/publishers/captcha-type-in
  * Olvasható reklámszlogent kell bemásolni
* https://www.mediawiki.org/wiki/Extension:QuestyCaptcha
  * Szöveges kérdés-válaszok
* https://www.drupal.org/project/captcha_pack
  * Többféle típus kombinációja
  * Példák: https://www.drupal.org/files/images/captcha_pack_examples.png
* https://django-simple-captcha.readthedocs.io/en/latest/
* https://github.com/Lokno/click-captcha
* https://github.com/hasadna/OpenCaptcha
* https://github.com/produck/svg-captcha
* https://gitlab.com/shaswata56/sKRATCHIE-Project
* https://github.com/librecaptcha/lc-core

### Google reCAPTCHA

kritika:

* https://github.com/neuroradiology/InsideReCaptcha
* https://fastcompany.com/90369697/googles-new-recaptcha-has-a-dark-side

### hCaptcha

* https://www.hcaptcha.com/
* A Cloudflare is lecserélte a Google reCAPTCHA-t erre
  * https://blog.cloudflare.com/moving-from-recaptcha-to-hcaptcha/

### FriendlyCaptcha

* https://friendlycaptcha.com/

### GeeTest

* https://www.geetest.com/en

### Arkose Labs FunCaptcha

* https://www.arkoselabs.com/
* also used by GitHub

### KeyCaptcha

* https://www.keycaptcha.com/

### mCaptcha

* https://mcaptcha.org/
* proof of work

### Capy

* https://capy.me/

### TikTok

* egyedi privát implementációjuk van

### Saját CAPTCHA ötletek

[Mechanical Turk HIT](https://en.wikipedia.org/wiki/Amazon_Mechanical_Turk) módszerei által inspirálva:

* Időre és hálózati ujjlenyomatra korlátozott feladatrészhalmaz
* Kliensek bizalmi szint alapján való párosítása
* Küldeni kell olyan kérdést is amire már korábban többen egyetértettek a megoldásban és olyat is amire nem ismerjük a megoldást.

#### OpenStreetMap POI név

* Mapillary, KartaView, Wikimedia Commons, Flickr, stb fotók alapján bolt nevének megadása.
* A legtöbb Mapillary képen nincs semmi érdekes, így gépi előszűrés kellene. A pozíció és irányultság is néha rossz.
* A bolt nevénél kis/nagybetű és egybe/különírástól eltekintve kevéssé számítok variációra (esetleg valaki lehagyja a strapline=*-t, de az mindegy): ha valaki a "Cserpes tejivó" helyett azt írja be, hogy "kocsma", annak ellenére, hogy ki van írva a homlokzatára, az simán egy rossz válasz.

#### OpenStreetMap POI típus

* Fotók alapján bolt típusának kiválasztása. Azért egy rövid felsorolásból (pl. 9 elem) csak ki tudja választani, hogy "semmi", "kereskedelmi egység", "méz eladó", "park"... Aztán a kategóriákon belül egy újabb részfeladat finomítana a típusára (bolt, étterem, posta, szépségszalon, ...). Szinonimákig még lehet géppel kereszt-validálni a megoldók között.
* Lehetne egy szinonimákat támogató, fotókkal megtűzdelt szöveges autocomplete mező. Azért tegyük a szívünkre a kezünket, és valljuk be, hogy az érdekes POI-k nagyságrendje megáll pár tucatnál, és mindig ott van az "Egyéb" gomb és mellette egy szövegdoboz, amit később egy szakértőbb (vagy akár térképész) fel tudna dolgozni Note/fixme alapon.
* Arra kisebb esélyt látok, hogy egy felhasználó mindhárom képfeladványa "Egyéb" kategóriába esne, és utána a keresztvalidáló felhasználók többsége szintén mindet "Egyébnek" címkézte és mindenki mindenhová más szöveget írt.
* Adott crawler le tudja gyűjteni a potenciális POI-kat a netről, és utána ezeket is kategorizáltathatjuk vagy fotók alapján validáltathatjuk emberekkel, és ilyenkor már eléggé le van szűkítve a lehetőségek száma (valószínűségek szerint sorba rendezve nem lehetetlen felajánlani a top 10-ben).

#### Egyéb lehetséges feladatok

* ház alapjának légifotó alapú berajzolása
* hiányzó házas rész jelzése
* ofszet megállapítás
* hiányzó út
* Szövegesek (elgépelés a címkeértékekben, ismeretlen kulcsok sanity ellenőrzése, töltsd ki a POI adatait a weboldala alapján, él-e még a POI külső weboldalak vagy hírek alapján, fordíts le vagy ellenőrizz egy mondatot az OSM wikiről vagy a Wikipédiából) 

#### Ismeretlen válasz ellenőrzése

* Növelhető a kinyerhető információ a megengedhető hibaarány csökkentésével
* Ha nem találunk elég gyorsan ellenőrző párt, elfogadhatjuk a választ
* Világméretű rendszereknél működhet valós időben is
* A portál megnyitásakor azonnal feltenni a kérdést, hogy legyen az email megerősítés küldése és első bejelentkezés előtt pár perc
* Lehetne email megerősítés során jelezni ha pár percen belül sikerült helyteleníteni a választ és ki kell tölteni egy újat.

#### JavaScript nélküli CAPTCHA

* Hagyományosan dinamikus tárhelyet igényelnek: szerver oldali scripteket és adatbázist
  * A JavaScriptet sok esetben kötelezővé teszik böngésző ujjlenyomatvétel okán, de egy sémát nem gyengítene jelentősen ennek hiánya sem
* Alternatívaként könnyített formában SSI (`.shtml`) illetve `.htaccess` alapú megvalósítás is lehetséges ami statikus tárhelyen is működhet
  * Időre és hálózati ujjlenyomatra korlátozott feladatrészhalmazt kell visszaadnia
  * A brute force ellen a hálózati rate limitingnek kell védenie

## Kijátszás

* https://en.wikipedia.org/wiki/CAPTCHA#Circumvention
* Gépi felismerés
  * https://capmonster.cloud/
* A legolcsóbb és legcélravezetőbb rövid- és középtávra ha simán felbérelünk embereket
  * https://github.com/jumper423/decaptcha
  * https://2captcha.com/blog/solve-hcaptcha
  * https://2captcha.com/2captcha-api#rates
  * https://anti-captcha.com/
  * http://bypasscaptcha.com/
  * http://captcha24.com/
  * https://www.deathbycaptcha.com/
  * https://expertdecoders.com/
  * https://www.imagetyperz.com/
  * http://pixodrom.com/
  * https://ripcaptcha.com/loc=en
  * https://rucaptcha.com/
  * http://www.socialink.ru/
