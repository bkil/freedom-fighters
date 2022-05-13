# Email postafiók kiszolgálás

## Összehasonlítások

* https://en.wikipedia.org/wiki/Comparison_of_mail_servers
* https://en.wikipedia.org/wiki/List_of_mail_server_software
* https://en.wikipedia.org/wiki/Message_transfer_agent

## Szerverek

* postfix+dovecot
* https://en.wikipedia.org/wiki/Message_transfer_agent

### Haraka

* https://haraka.github.io/
* SMTP szerver
* node.js
* állítólag csak pár MB RAM-ot eszik és villámgyors
* teljesen testre szabható: DKIM 1 sor a beállításokban, egy centralizált, teljesen egyedi bejelentkezéskezelést is lehet írni bővítményként pár tucat sorból

## Telepítők

* https://mailcow.email/
* https://mailinabox.email/
* https://mailu.io/
* https://github.com/jeekkd/iRedMail-scripts
* Lásd még: [packages.md](packages.md)

### Telepítési útmutatók

* https://poolp.org/posts/2019-09-14/setting-up-a-mail-server-with-opensmtpd-dovecot-and-rspamd/
* https://github.com/deltachat/sysadmin/blob/master/guides/mailserver.md

## Kézbesíthetőség

* Már az első levél kiküldés előtt legyen minden jól beállítva
* Legyen tiszta az IP címünk és domain nevünk
  * https://mxtoolbox.com/blacklists.aspx
  * https://en.wikipedia.org/wiki/Comparison_of_DNS_blacklists
* Saját domain név amin normális tartalom van és van indexelve
* PTR rekord
* DKIM, SPF, DMARC
* Bejáratás
  * 1-2 hétig
  * Enedélyezzük a napi DMARC reportot
  * Napi 1-2 levél kiküldése különféle nagy szolgáltatók irányába, arra válaszok, illetve "nem spam" gomb benyomása, lehetőleg adott külső címről először fogadjunk levelet, és csak azután küldjünk rá választ
  * `In-Reply-To` és `subject` fejléc alapú szál fenntartása
  * Különféle webmail, asztali és mobil klienssel
  * Akár különféle levlistákra feliratkozás, arra üzenetek küldése
  * Lehetőleg ne legyen egyáltalán spam gyanús: angolul (és/vagy magyarul?), ne legyen benne HTML, képek, linkek, rossz szavak, zagyva szöveg

### Kézbesíthetőségi útmutatók

* https://sendersupport.olc.protection.outlook.com/pm/troubleshooting.aspx
* https://arstechnica.com/information-technology/2014/02/how-to-run-your-own-e-mail-server-with-your-own-domain-part-1/
* https://arstechnica.com/information-technology/2014/03/taking-e-mail-back-part-2-arming-your-server-with-postfix-dovecot/
* https://arstechnica.com/information-technology/2014/03/taking-e-mail-back-part-3-fortifying-your-box-against-spammers/
* https://arstechnica.com/information-technology/2014/04/taking-e-mail-back-part-4-the-finale-with-webmail-everything-after/
* https://www.reddit.com/r/selfhosted/comments/cdutjt/self_hosted_email_understanding_dmarc/etwo3re/?context=3
