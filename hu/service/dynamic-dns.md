# Dinamikus DNS

## Hátrányok

Nem érdemes publikus szervert üzemeltetni ilyen név alatt:

* Alacsony TTL, gyakran 60 másodperc, emiatt kevésbé hatékony böngészéskor a gyorsítótárazás
  * Tipikusan lassú névfeloldás a világ egyes részein
* Kockázat ha nem ismerjük az üzemeltetőt:
  * Közbeékelés lehetősége
  * Bármikor megszűnhet, ezzel magával rántva minket és az összes felhasználónkat, beleértve a reputációikat
  * Komplexitás miatt alacsonyabb az SLA mint egy normál névszerver esetén
  * Ismeretlen tartalomszűrési irányelvek és DDoS védelem
* A fő domain vagy az az alatti másik, rosszindulatú aldomain egyes tevékenységeinek reputáció miatt minket is büntethetnek (SEO, tartalomszűrők)
* Eleve a változó DHCP IP címünk hátrányosan meg lesz különböztetve (például levelezőszerverek által)

## Névtelen szolgáltatók

Nem tartanak nyilván regisztrációnként személyes adatokat vagy email címet, csak egy kívánt aldomain nevet és egy jelszót:

* https://freemyip.com/
