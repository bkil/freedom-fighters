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

### Freemail

* https://freemail.hu/
* 10GB tárhely
* érdekeltség: Magyar Telekom Nyrt.

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
* érdekeltség: Indamedia csoport
* választható végződések: indamail.hu, vipmail.hu, webmail.hu
* további szolgáltatások:
  * Index.hu, Totalcar.hu, Totalbike.hu, Nepitelet.hu, Divany.hu, Femina.hu, Port.hu, Indavideo.hu, Blog.hu, Indamail.hu, Forum.index.hu, Indafoto.hu, Penge.hu, Indafax.hu
  * Velvet.hu, Konyvek.index.hu, Totalcarmagazine.com, Napi.hu, konferenciak.napi.hu, Retikul.hu, Noifriss.hu, Feminamedia.hu, Feminaklub.hu, Színház.hu, FeminaShop.hu, otthonterkep.hu, ingatlantajolo.hu, irodahaz.info, raktar.info

### Citromail

* https://www.citromail.hu/
* 2GB tárhely
* max. 5MB/csatolmány
* TODO: IMAP, POP3
* érdekeltség: Sanoma Budapest Zrt.

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
* https://en.wikipedia.org/wiki/Comparison_of_webmail_providers#General
* https://github.com/arnt/freemail
* https://gist.github.com/tbrianjones/5992856
* https://github.com/igor-alexandrov/ped/blob/master/lib/ped/domains.rb
* https://github.com/Kikobeats/free-email-domains/blob/master/domains.json
* https://github.com/goware/emailproviders/blob/master/generate/domains.txt
* https://gist.github.com/jpadilla/8468419 (2014)

## Megszűnt

* https://www.tvn.hu/reg/reg2.tvn (TVN.hu Kft.)

## Pingback

Ha átnevezésre vagy áthelyezésre kerül ez a fájl, az összes közvetlen hivatkozást frissíteni kell:

* https://hup.hu/comment/2563434#comment-2563434
