# Email szolgáltatások

## Szempontok

Többféle célcsoportunk különböző, de kapcsolódó igényekkel rendelkezik:

* Legyen fenntartható, ne csődöljön be mostanában: például üzemeljen már egy ideje és legyen hihető üzleti modellje
* Minden elérhető legyen magyarul (ÁSZF, regisztráció, terméktámogatás, esetleg webmail)
* Magyar földön legyen üzemeltetve
* Magánszférát tiszteletben tartó, jogbiztonsággal rendelkező országban legyen üzemeltetve

## Aliasok

* https://en.wikipedia.org/wiki/Email_address#Common_local-part_semantics

A spam elleni küzdelem és a személyes adatok védelme érdekében sokszor elkülönített címeket is ki tudunk adni amire beérkező leveleket ugyanazzal az egy fiókunkkal tudunk kezelni.

Egyes szolgáltatóknak egy prémium funkciója és a felületükön be lehet állítani erre átirányítást illetve a feladó címének állítását.

### Fogadás

Technológiai okokból elképzelhető, hogy akkor is megérkezik egy levél a fiókunkba, ha azt a címünk bizonyos torzított változataira adták fel.

* Subaddressing ("alcímzés"): fióknevünk után (és a "@" elé) bizonyos karaktersorozattal elválasztva tetszőleges szöveg beírható. Ez különféle szolgáltatóknál tipikusan lehet: "+", "-", "--", "%", "=", "/", de az [RF5233](https://tools.ietf.org/html/rfc5233) szerint a szolgáltató által választott bármilyen megengedett jel állhatna itt. Lásd: [../article/email-address-syntax.md](../article/email-address-syntax.md)
* Ekvivalencia: néha a kis- és a nagybetűs változat is egyenértékű, illetve további karakterek egyszeri vagy többszöri beékelése a fióknévbe szintén figyelmen kívül hagyott, gyakran ezek: ".", "-", "_", "\".
* Nehezítés, hogy a legszigorúbb validátorok csak ezt fogadják el a lokális fióknév részben a @ előtt: `[0-9a-zA-Z_.-]`, de még a "+" és "%" is gyakran támogatott.

### Küldés

## Magyarországon ingyen

### c2 webmail

* https://www.c2.hu/new_user_registration/index.html
* üzemeltető: OFFICEline Magyarország Kft.
* legrövidebb használható felhasználónév: 2 karakter
* webmail, IMAP, POP3, SMTP
* 100MB tárhely regisztráció után, de minden nap "használat" (belépés?) után emelkedik egészen 10GB-ig
* ha nem történik sem webmail belépés, sem kliens lekérés:
  * 90 (60?) nap után nem fogad új leveleket (inaktiválódik)
  * 270 nap után törlődik minden adat
  * bármikor újra be lehet lépni
* megszüntetett fiók újra nem regisztrálható
* belépési adatokat (időpont, IP cím) 1 évig tárolnak

### Freemail

* https://freemail.hu/
* 10GB tárhely
* üzemeltető: Mediaworks Hungary Zrt. (korábban: New Wave Media Group Kft.)
* érdekeltség: Magyar Telekom Nyrt.
* láthatatlan Google ReCaptcha bejelentkezésnél

### GMail.hu

* https://gmail.hu/
* üzemeltető: Egonet Work Kft.
* 1GB tárhely
* webmail, mobil, POP3, SMTP
* @gportal.hu végződés is elérhető
* 120 naponta be kell lépni

### indamail

* https://indamail.hu/
* 2GB tárhely, legfeljebb 1GB-es levélcsatolmány
* POP3, IMAP
* korábbi nevén: VIPmail, Indexmail, DrótPostaGalamb
* tulajdonos: Inda-Labs Magyarország Zrt.
* érdekeltség: Indamedia csoport (hirdetések)
* üzemeltető: Media Future Technológiai Szolgáltató Zrt., Fjordmail (korábban: Citromail)
* választható végződések: indamail.hu, vipmail.hu, webmail.hu
* 120 naponta be kell lépni a weboldalon, különben felfüggesztik a levélfogadást
* további szolgáltatások:
  * Index.hu, Totalcar.hu, Totalbike.hu, Nepitelet.hu, Divany.hu, Femina.hu, Port.hu, Indavideo.hu, Blog.hu, Indamail.hu, Forum.index.hu, Indafoto.hu, Penge.hu, Indafax.hu
  * Velvet.hu, Konyvek.index.hu, Totalcarmagazine.com, Napi.hu, konferenciak.napi.hu, Retikul.hu, Noifriss.hu, Feminamedia.hu, Feminaklub.hu, Színház.hu, FeminaShop.hu, otthonterkep.hu, ingatlantajolo.hu, irodahaz.info, raktar.info

### Citromail

* https://www.citromail.hu/
* 2GB tárhely
* max. 5MB/csatolmány
* TODO: IMAP, POP3
* hirdetések: Central Média, Adverticum, Google
* üzemeltető: Fjordmail International (korábban: Central Médiacsoport Zrt.)
  * https://www.fjordmail.no/fjordmail-acquires-citromail-in-hungary/
* utolsó belépést követő:
  * 110 nap után nem fogad leveleket
  * 240 nap után törlődik minden levél
  * 720 nap után nem lehet belépni
  * https://www.citromail.hu/adatvedelmi-nyilatkozat/aktualis

### euromail

* https://www.euromail.hu/
* 50MB tárhely
* csak webmail (nincs IMAP/POP3/SMTP)
* Google Captcha regisztrációnál és sokszor bejelentkezésnél is
* érdekeltség: Humankraft Kft. (független)
* nem támogatott ekvivalencia: ".", "-", "_"
* nem támogatott subaddressing alias: "%", "=", "-", "+"
* támogatott ekvivalencia: kis-nagybetű, "\", "\\"

## Magyarországon fizetős

* https://www.mikrovps.net/hu/email-hosting/basic 15GB tárhely, 3000 Ft+áfa/év (0.89 EUR/hó) (MikroVPS Kft.)
* https://megacp.com/hosting.php?aid=urb40687&spt=1 Induló tárhely csomag, 500 MB tárhely, saját domén, korlátlan címek, 5600 Ft + ÁFA / 2 év (bruttó 300 Ft/hó) (3 in 1 Hosting Bt.)
* https://www.forpsi.hu/email/ bruttó 1905 Ft/év domén mellé, 1GB
* https://mailbox.hu/ 1 EUR/hó
* https://www.mhosting.hu/tarhely email csomag 1892Ft/év+áfa, 250MB
  * támogatott ekvivalencia: kis-nagybetű, "\", localpart idézőjelezés
  * nem támogatott: ".", "-", "%", "+"

## Magyarországon másodlagos email cím ingyen

Regisztrációhoz meglévő működő elektronikus levélcím szükséges, viszont mondjuk az elsődleges címhez képest további vagy jobb szolgáltatásokat biztosít.

* https://www.nethely.hu/ingyenes-tarhely
* https://atw.hu/ingyenes-webtarhely

## Etikus országban ingyen

* https://tutanota.com/ Németország, csak webmail ingyenes, 1GB tárhely
* https://disroot.org/en/services/email Hollandia, nem alanyi jogon jár, regisztrációhoz átmenetileg szükséges egy elsődleges email fiók megadása

### Protonmail

* http://protonmail.com/ Svájc, csak webmail ingyenes, 500MB tárhely, 150 üzenet/nap
* támogatott ekvivalencia: ".", "-", kis-nagybetű
* támogatott subaddressing: "+"

## Etikus országban másodlagos email cím ingyen

* https://webmail.vivaldi.net/ 5GB tárhely, max. 20MB/csatolmány, webmail, IMAPs, SMTPs, POP3s, 6 hónap után a weben inaktív fiókokat törlik, Norvégia (Vivaldi Technologies AS)

## Etikus országban fizetős

* https://mailbox.org/ 1 EUR/hó, 2 GB levelezőtárhelyet, 100 MB felhőtárhely, webmail, IMAP, WebDAV/CalDAV/CardDAV címtár és naptár, Open-Xchange, Németország (Heinlein Support GmbH)

## Csak Tor

* https://elude.in/
* http://mail2tor.com/
* https://dnmx.org/

## Külső összehasonlító oldalak

* https://www.fsf.org/resources/webmail-systems
* https://www.privacytools.io/providers/email/
* https://github.com/deltachat/eppdperf
* https://providers.delta.chat/
* https://en.wikipedia.org/wiki/Comparison_of_webmail_providers#General
* https://github.com/arnt/freemail
* https://gist.github.com/tbrianjones/5992856
* https://github.com/igor-alexandrov/ped/blob/master/lib/ped/domains.rb
* https://github.com/Kikobeats/free-email-domains/blob/master/domains.json
* https://github.com/goware/emailproviders/blob/master/generate/domains.txt
* https://github.com/renlight10/Email-verification-API/blob/master/trusted_domain.txt
* https://gist.github.com/mavieth/418b0ba7b3525517dd85b31ee881b2ec
* https://gist.github.com/jpadilla/8468419 (2014)
* https://gist.github.com/benstr/78e6a126849d12ceff22ffa614d7cf22
* https://github.com/andrebradshaw/regular_expressions/blob/master/personal_email_domain.txt
* https://digdeeper.neocities.org/ghost/email.html

## Megszűnt

* https://www.tvn.hu/reg/reg2.tvn (TVN.hu Kft.)

## Pingback

Ha átnevezésre vagy áthelyezésre kerül ez a fájl, az összes közvetlen hivatkozást frissíteni kell:

* https://hup.hu/comment/2563434#comment-2563434
* https://hup.hu/comment/2697779#comment-2697779
