# Szabad szoftvert futtató telefon

## Végcél

* Az összes lényeges forráskód átnézhető és javítható
* Minden használt szolgáltatás self-host (magunk által üzemeltethető) megoldásra cserélhető
  * Emiatt Google-mentes

## Köztes lépés az átállók érdekében

* Biztosítsuk, hogy minél több funkcionalitást tudjanak használni valamilyen alternatív módon és fokozatosan tudjanak átállni a nyílt alternatívákra
* Első bekapcsoláskor rákérdez, hogy mely régi alternatívákat rakjuk fel (később is előhívható ez a telepítő)
  * Play Store
  * Csak hibakeresésre, mert az alternatív elérési módjaik elég jónak kellene lenniük
    * Facebook
    * GMail
    * Google Maps
    * Google Search

## Népszerűsíteni kívánt alternatívák

* Play Store -> F-Droid
  * https://en.wikipedia.org/wiki/List_of_mobile_app_distribution_platforms
* Facebook Messenger, Kik -> Mátrix cset
* VoIP (Viber, WhatsApp, Skype, SnapChat  ->)
  * Signal, Linphone (SIP), Conversations/ChatSecure/Gajim (XMPP), Mátrix (Jitsi)
  * (Miután stabil: Jami, Tox, Wire)
* Facebook -> Friendica/Hubzilla/Diaspora
* Twitter -> Friendica/Pleroma/Mastodon
* Instagram -> PixelFed
* Google Search -> Qwant/Searx/DuckDuckGo
* GMail -> Protonmail/Tutanota/Disroot/(vagy tetszőleges SMTP/IMAP a [helyi országból](../service/email-account.md))
* Google Maps -> OpenStreetMap (OSMand, MAPS.me, Navit, Mapy.cz)
* YouTube -> PeerTube/BitChute
  * https://f-droid.org/packages/app.fedilab.nitterizeme/ UntrackMe: Twitter/YouTube átirányításhoz
  * https://f-droid.org/en/packages/app.fedilab.tubelab/ PerTube
  * https://f-droid.org/en/packages/net.schueller.peertube/ PeerTube
* Evernote -> https://joplinapp.org/

## Régi szolgáltatások átmeneti eléréséhez

Kompatibilis módszerek a régen használt szolgáltatások átmeneti használatára az áttérés befejezéséig

* GMail: SMTP/IMAP vagy akár a webmail
* Youtube:
  * mobil böngészőből
  * https://github.com/omarroth/invidious
  * https://f-droid.org/en/packages/org.schabi.newpipe/
  * https://f-droid.org/en/packages/su.sadrobot.yashlang/
  * https://f-droid.org/en/packages/free.rm.skytube.oss/
  * https://f-droid.org/en/packages/deep.ryd.rydplayer/
* Facebook Messenger: asztali webes
  * https://f-droid.org/packages/org.surrel.messengerbypasser
* Facebook: speciális, izoláló böngésző
  * https://f-droid.org/packages/me.zeeroooo.materialfb/
* Twitter
  * https://f-droid.org/packages/com.github.moko256.twitlatte/
* Google Maps: böngészőből
  * Csetekre Mátrix kliens + Mátrix-bridging (pl. Slack, Discord, Telegram, FB messenger)
* Instagram
  * https://f-droid.org/packages/awais.instagrabber/
  * Asztali: https://github.com/terkelg/ramme

## Zárt alkalmazások telepítéséhez

Ha valamire nem létezik alternatíva és muszáj feltenni az eredeti programot mondjuk teszteléshez. Sérti minimum az ÁSZF-et, esetleg szerzői jogokat és DMCA-t is.

* https://github.com/ImranR98/Obtainium
* https://github.com/accrescent/accrescent
* https://f-droid.org/en/packages/com.github.yeriomin.yalpstore/
* https://f-droid.org/en/packages/com.aurora.store/

## Informatikusoknak

* https://en.wikipedia.org/wiki/Rooting_(Android)
* https://en.wikipedia.org/wiki/Comparison_of_mobile_operating_systems
* https://en.wikipedia.org/wiki/List_of_open-source_mobile_phones
* https://en.wikipedia.org/wiki/List_of_custom_Android_distributions
* https://en.wikipedia.org/wiki/Category:Custom_Android_firmware
* https://en.wikipedia.org/wiki/Category:Android_forks

### Linux alkalmazások mobilon

* https://en.wikipedia.org/wiki/Termux
* https://en.wikipedia.org/wiki/UserLAnd_Technologies
* https://en.wikipedia.org/wiki/OS_virtualization_and_emulation_on_Android#Emulation
