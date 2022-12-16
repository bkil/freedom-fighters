# Elosztott szoftverfejlesztési projekt tárolók

Olyan etikus projekt tároló portál (VCS hosting) ami mind ingyenesen hostolt szabad célokra mind magunk által is üzemeltethető ha migrálnánk.

Azon szolgáltatóknál ahol nincs CI/CD vagy statikus webkiszolgálás, sokszor harmadik fél által üzemeltetett szolgáltatásként is beköthető:

* [service/free-continuous-integration.md](service/free-continuous-integration.md)
* [../free-static-web-hosting.md](../free-static-web-hosting.md)

## Régi, nagy publikus szereplők

### GitLab.com

* https://gitlab.com/
* gazdag az API-ja
  * https://docs.gitlab.com/ee/api/
* CI/CD, statikus webkiszolgálás
* cenzúrázva: Kuba

### Savannah

* https://savannah.gnu.org/
  * https://savannah.nongnu.org/
  * https://git.savannah.gnu.org/cgit/administration/savane.git/
* nincs kifejezett REST API, de a frontendről elérhetők a projekt menedzsment funkciók és levelezés
  * https://savannah.gnu.org/maintenance/SavannahInternals/
* cenzúrázatlan: Kuba

### LaunchPad.net

* https://LaunchPad.net/
* fiók: Ubuntu One
* REST API funkciók: projekt menedzsment, hibajegy kezelés
  * https://help.launchpad.net/API/Hacking
* Bazaar, Git
* cenzúrázatlan: Kuba

### Pagure.io

* https://Pagure.io/
* fiók: Fedora FAS
* REST API funkciók: projekt menedzsment, PR és hibajegy kezelés
  * https://src.fedoraproject.org/api
* cenzúrázatlan: Kuba

### SourceForge.net

* https://sourceforge.net/
  * forrás: https://allura.apache.org/
* REST API funkciók: hibajegyek, üzenetek, wiki oldal és blogbejegyzés
  * https://forge-allura.apache.org/docs/getting_started/administration.html#public-api-documentation
* cenzúrázva: Kuba

### Debian Salsa GitLab

* engedélyezve az összes GitLab szolgáltatás, beleértve a CI/CD és Pages (https://*.pages.debian.net/)
* https://wiki.debian.org/Salsa/Doc#Web_page_hosting
* https://wiki.debian.org/Salsa/FAQ#How_can_I_use_salsa.debian.org_without_JavaScript.3F

> What can be hosted on salsa? The answer is simple: As long as it is opensource and/or can be included in Debian, it is fine to use salsa. If in doubt, ask.

## Új, kis szereplők

### ChiselApp.com

* https://chiselapp.com/
* Fossil SCM

### codeberg.org

* 2019
* motorja: gitea
* feldolgozás nélküli statikus webkiszolgálás (Gitea Pages)
* helyszín: Németország
* cenzúrázatlan: Kuba
* CI/CD kutatás alatt
  * Woodpecker CI - Drone.io fork
  * https://codeberg.org/Codeberg-CI/request-access

### Gitea.com

* 2019
* motorja: gitea
* helyszín: Kína
* wiki
* gazdag REST API funkciók: projekt menedzsment, hibajegyek, változáscsomagok, fájlok létrehozása
  * https://docs.gitea.io/en-us/api-usage/
* cenzúrázatlan: Kuba

### NotABug.org

* motorja: Gogs https://gogs.io/
* https://notabug.org/hp/gogs
* helyszín: Németország
* a REST API csak olvasni tud fájlokat, ezt leszámítva teljes értékű
  * https://github.com/gogs/docs-api
* cenzúrázatlan: Kuba

### gogs

* a kérdés, hogy a NotAbug.org frissítette-e a forkját, vagy a régit használja
* gazdag REST API funkciók (2022 óta fájl írással)
  * https://github.com/gogs/docs-api
  * https://github.com/gogs/gogs/pull/7114

### teknik.io

* motorja: gitea
* cenzúrázatlan: Kuba

## Korlátozott tagsággal

A regisztrációkat tipikusan egyenként hagyják jóvá az üzemeltetők.

### git.disroot.org

* Amszterdam

### framagit.org

* Franciaország

### libregit.org

* jelenleg csak meghívóval lehet csatlakozni

### SourceHut.org

* motorja: Sourcehut
* CI/CD
  * https://man.sr.ht/builds.sr.ht/compatibility.md
* az API csak webhook és felhasználói beállításokra használható
  * https://man.sr.ht/api-conventions.md
* később fizetősnek tervezik

## Negatív példák

### GitHub.com

* https://github.com/
* gazdag az API-ja
  * https://docs.github.com/en/free-pro-team@latest/rest
* CI/CD: GitHub Actions
  * https://github.com/features/actions
* statikus webkiszolgálás
* nem magunk által üzemeltethető
* üzemeltető: Microsoft
* cenzúrázatlan: Kuba

### BitBucket.com

* https://bitbucket.com/
* gazdag az API-ja
  * https://developer.atlassian.com/server/bitbucket/reference/rest-api/
* CI/CD
  * https://bitbucket.org/product/features/pipelines
  * https://www.atlassian.com/software/bitbucket/pricing
  * 50 perc/hó futás
* statikus webkiszolgálás
* nem magunk által üzemeltethető
* üzemeltető: Atlassian
* cég: Ausztrália
* cenzúrázatlan: Kuba

## Külső hivatkozások

* https://www.ubuntubuzz.com/2020/02/ethical-code-hosting-services-in-2020.html
* https://www.gnu.org/software/repo-criteria-evaluation.html
* https://en.wikipedia.org/wiki/Comparison_of_source-code-hosting_facilities
