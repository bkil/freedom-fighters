# HTTPS használata

A kérdés, hogy mik az előnyei annak ha weboldalunkat HTTPS alól tesszük elérhetővé HTTP helyett?

Ebbe beleértjük a különféle SSL/TLS verziókat a HTTP alatt.

## Hátrányok

### Tanúsítványok költségei

* Pénzbe kerülhet a tanúsítvány maga
* Pénzbe kerülhet a tanúsítványt kezelő bővítmény a vezérlőpulton és/vagy a PaaS szolgáltatónknál ez a képesség
* Aki jelenleg ingyen vagy kedvezményesen adja, bármikor meggondolhatja magát és miután megszoktuk, a beetetés után elkezdheti drágán adni

### Körülményesebb telepítés

Időbe kerül beállítani, kitesztelni és karbantartani.

* TLS tanúsítvány igénylése, automatikus megújítása, webszerver beállítása
* https://en.wikipedia.org/wiki/OCSP_stapling
  * https://blog.mozilla.org/security/2015/11/23/improving-revocation-ocsp-must-staple-and-short-lived-certificates/
  * https://securemachinery.com/2017/10/09/ocsp-validation-and-ocsp-stapling-with-letsencrypt/
* https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization
* https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security
* https://hstspreload.org/
* https://en.wikipedia.org/wiki/URL_redirection#Forcing_HTTPS
* További finomhangolás amennyiben régi végfelhasználói eszközöknek típusok szerint kézzel felsorolva szeretnénk engedni kevésbé biztonságos elérést

### Osztott webszervereken

Körülményesebb virtuális kiszolgálókon (megosztott webszerveren és IP címen)

* Nem minden szolgáltató hajlandó beállítani
* Minden bérlőnek új tanúsítványt kell igényelnie
* TLS 1.3 körüljárás: ECH/ESNI
  * https://en.wikipedia.org/wiki/Server_Name_Indication#Encrypted_Client_Hello

### Reverse proxy

* Reverse proxy cache illetve CDN beállítása is körülményesebb
* Erre wildcard tanúsítvány sem elég: multi-domain kell, külön IP címekkel (Subject Alternative Name)

### Caching proxy

* Gyakorlatilag nem proxy-zható a végfelhasználókhoz közelebb
* Internet szolgáltatóknál vagy kisközösségeknél nem lehet enélkül csökkenteni a sávszélességigényt és késleltetést
* Céges hálózaton biztonsági szűrők
* Csak közbeékeléssel amihez minden végfelhasználói eszközön módosítani kell (tanúsítványtár és/vagy a böngészőben is)
* Lehetséges volna NULL cipher felhasználásával (hitelesítésre, titkosítás nélkül), de ez nem támogatott:
  * https://hamwan.org/Standards/Network%20Engineering/Authentication/SSL%20without%20Encryption.html

### Mixed content warning

* Figyelmeztetések vagy meghiúsult hozzáférés ha egyes assetek, modulok, reklámok HTTP-re is hivatkoznak
* Néha külső függéseink hozzák be amire nincs ráhatásunk
* User Generated Content is érintett: amikor egy platformon a bejegyzésekben külső hivatkozásokkal szeretnének beágyazni, ami ellen néha egy lokális proxy működő körüljárás lehet, de nem mindenhol skálázódik jól

Körüljárásokért lásd:

* [../../en/article/circumvent-https-mixed-content.md](../../en/article/circumvent-https-mixed-content.md)

### Lassabb oldallekérések

* Egy idő után az első oldallekérésnek jelentősen nagyobb a késleltetése (képességek egyeztetése, kulcsgenerálás, tanúsítvány ellenőrzés)
  * Valamelyest ellensúlyozza: HTTP/2, HTTP/3 (QUIC), HTTP 1.1 Pipelining, Keep-Alive, TLS False Start, TLS 1.3 0-RTT SSL Early Data, session cache, session tickets, OCSP Stapling, dinamikus rekordméretezés
  * Súlyosbítja: interkontinentális távolság vagy gyengébb térerejű vezeték nélküli kapcsolat (lassú mobilnet, túlterhelt vagy zavart wifi)
* Minden oldallekérés tovább tart: egy kis konstans RTT és pár kilobájt
* Valamelyest ellensúlyozhatja ha a bizalmasságot feladva igénybe veszünk CDN-eket a statikus tartalmakra

### Többlet erőforrásigény

* A titkosítás platformtól függően egy kis processzor- és fogyasztástöbbletet okozhat minden átküldött adatra
* Publikus kulcsú titkosítási rész: kliens oldalon kevésbé, szerver oldalon jobban
* Osztott kulcsú titkosítás: hasonlóan terheli mindkettőt
* Súlyosbítja: böngészők párhuzamosan akár 6 kapcsolatot is nyithatnak ugyanarra a szerverre
* Nagyban függ a használati esettől, számítás vs. kiszolgálási idő, új látogatók száma
* 2021-es asztali CPU-kon ez már csak pár százalék
  * Régi vagy beágyazott rendszereken több
  * https://en.wikipedia.org/wiki/Cipher_suite#Cipher_suites_for_constrained_devices

### Régi eszközök támogatása

* A biztonsági döntések régi végfelhasználói eszközök kizárását jelentik
  * Régi TLS verziók
  * HTTP átirányítás és HSTS

### Szerződési feltételek

* Ez egy újabb ÁSZF és GDPR adatkezelési nyilatkozat amit mind az üzemeltetőnek, mind a felhasználónak el kell fogadnia
* Üzemeltető
  * Regisztrációkor személyes adataink megadása
  * Regisztráció után az _igénylő_ gépének IP címét publikálják: ha például manuális módban máshol igényeljük mint ahová majd telepítjük
  * Jogi felelősség vállalása
  * A szerverünket és azon futó szoftvereket folyamatosan nyomon követik
  * Weboldalunk látogatottsága és közössége alapján ránk is levonhatnak következtetések, amit súlyosbíthat a weboldal publikus DNS bejegyzése
    * Még ha a szerződés szerint a látogatókról személyes OCSP profilt nem is építenek, gyakorlatilag az üzemeltetőről ezt már megtehetik, például ha tüntetések idején bizonyos helyszínekről bizonyos demográfiák nagy számban látogatják oldalunkat
  * Az összegyűjtött profil legfeljebb 10 évig tárolható és semmilyen törlési kérésnek nem tudnak engedni
  * A tanúsítványunk egy nyilvános listára is felkerül
    * https://en.wikipedia.org/wiki/Certificate_Transparency
  * A tanúsítványkibocsátónk adatvédelmi nyilatkozata bármikor egyoldalúan változhat, emiatt az üzemeltetőnek folyamatosan figyeltetnie kell, a változásokat publikálni a saját oldalán és/vagy amennyiben a módosítás igényli, cselekedni
  * https://letsencrypt.org/documents/LE-SA-v1.2-November-15-2017.pdf
* Látogató
  * Tanúsítványlánc bejárása
  * OCSP ellenőrzés során: IP cím, böngésző, operációs rendszer és egyéb metaadat
    * https://en.wikipedia.org/wiki/TCP/IP_stack_fingerprinting akár aktívan is vehetnek ujjlenyomatot a látogató gépéről
    * _Elméletileg_ ha a tanúsítványkibocsátónál (és kollaboránsainál) tárolt adatokat profillá szervezik, következtethetnek a böngésző bővítményekre vagy gyorsítótárazás alapján szokásokra a végrehajtott vagy kihagyott oldalbetöltésekből.
  * https://letsencrypt.org/privacy

### Cenzúra

* A kibocsátó bármikor visszavonhatja a tanúsítványunkat, ezzel gyakorlatilag elérhetetlenné téve az oldalt
* OCSP ellenőrzés esetén ezt akár látogatónként is személyre szabhatják
* _Elméletileg_ közrejátszhatnának látogatóink közbeékelésében is személyre szabott hátsó ajtókkal

### Nyomkövetés OCSP útján

* https://en.wikipedia.org/wiki/Online_Certificate_Status_Protocol#Comparison_to_CRLs
  * Kiadja harmadik személyeknek, hogy ki mikor mit nézeget
  * Titkosítatlan csatorna, így az internet szolgáltatónknak és más megfigyelők számára is nyitott
  * Nagy terhet ró a központi infrastruktúrára
  * Korlátozott visszajátszási támadás: bár támogat nonce-ot, a szerverek egy része napokra gyorsítótárazza a válaszokat teljesítményi megfontolásokból
* Körüljárás:
  * Az üzemeltetőnek be kell állítania OCSP stapling-et a lánc minden tanúsítványára
  * Blokkolni az OCSP kéréseket a felhasználó gépén (CRL fallback)

### Nyomkövetés HSTS útján

* https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security#Privacy_issues

## Előnyök

### SEO

* SEO: egyes internetes keresők előnyben részesítik a találati listában

### Biztonságos csatornát megkövetelő funkciók

* Enélkül nem szabad vagy nem érdemes bizonyos szolgáltatásokat üzemeltetni (fizetés, belépés)
* A böngészők HTTPS nélkül letiltanak bizonyos funkciókat
  * HTTP `Secure` és `HttpOnly` süti attribútum: JavaScript kiolvasás ellen véd
  * HTTP/2 (és elődje az SPDY)
  * brotli tömörítés: állítólag régi proxy-k és víruskeresők elleni körüljárás akik rosszul kezelték a nem-gzip és nem-deflate tartalmakat - megakadályozza a közbeékelést
  * fizetés (Payment Request API)
  * helymeghatározás (Geolocation API)
  * tervben van: gyorsulásérzékelő
  * alkalmazás gyorsítótár (Service Workers)
  * jelszókezelés (Credential Management API)
  * médiafolyam rögzítés (Media Capture and Streams API)
  * médiatitkosítás (Encrypted Media Extensions API)
  * titkosítás (Web Cryptography API)
  * Bluetooth (Web Bluetooth API)
* https://w3c.github.io/webappsec-secure-contexts/#threat-risks
* https://blog.mozilla.org/security/2018/01/15/secure-contexts-everywhere/

### Közbeékelés elleni védelem

* idegen JavaScript és iframe beszúrás

###  Passzív megfigyelés elleni védelem

* milyen oldalakat böngésztünk
* bizonyos azonosítók, rossz implementációknál jelszavak is
* számítógépünk tulajdonságai

## Kétélű

* Enélkül bizonyos böngészők figyelemfelhívó jeleket jelenítenek meg
  * Hamis biztonságérzet
  * A weboldalba több bizalmat fektethet mint amennyit kellene
  * Bármelyik támadó tud ingyen hiteles oldalról kiszolgálni

## Források

Van amelyiknek az információtartama elévült, de az elméletet jól szemléltetik.

* https://istlsfastyet.com/
* https://hpbn.co/transport-layer-security-tls/#leverage-early-termination
* https://hpbn.co/building-blocks-of-tcp/#tcp-fast-open
* https://wiki.mozilla.org/Security/Server_Side_TLS#Recommended_Ciphersuite
* https://www.httpvshttps.com/ HTTP vs. HTTPS sebességmérő
* https://www.imperialviolet.org/2010/06/25/overclocking-ssl.html
