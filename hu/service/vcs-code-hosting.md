# Elosztott szoftverfejlesztési projekt tárolók

Olyan etikus projekt tároló portál (VCS hosting) ami mind ingyenesen hostolt szabad célokra mind magunk által is üzemeltethető ha migrálnánk.

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

## Új, kis szereplők

### codeberg.org

* 2019
* motorja: gitea
* helyszín: Németország
* cenzúrázatlan: Kuba

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
* helyszín: Németország
* cenzúrázatlan: Kuba

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
* később fizetősnek tervezik

## Negatív példák

### GitHub.com

* https://github.com/
* gazdag az API-ja
  * https://docs.github.com/en/free-pro-team@latest/rest
* CI/CD, statikus webkiszolgálás
* nem magunk által üzemeltethető
* üzemeltető: Microsoft
* cenzúrázatlan: Kuba

### BitBucket.com

* https://bitbucket.com/
* gazdag az API-ja
  * https://developer.atlassian.com/server/bitbucket/reference/rest-api/
* CI/CD, statikus webkiszolgálás
* nem magunk által üzemeltethető
* üzemeltető: Atlassian
* cég: Ausztrália
* cenzúrázatlan: Kuba

## Külső hivatkozások

* https://www.ubuntubuzz.com/2020/02/ethical-code-hosting-services-in-2020.html
* https://www.gnu.org/software/repo-criteria-evaluation.html
* https://en.wikipedia.org/wiki/Comparison_of_source-code-hosting_facilities
