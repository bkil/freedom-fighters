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
* van API CORS
* CI/CD, statikus webkiszolgálás
* cenzúrázva: Kuba

### Savannah

* https://savannah.gnu.org/
  * https://savannah.nongnu.org/
  * https://git.savannah.gnu.org/cgit/administration/savane.git/
* nincs kifejezett REST API, de a frontendről elérhetők a projekt menedzsment funkciók és levelezés
  * https://savannah.gnu.org/maintenance/SavannahInternals/
* cenzúrázatlan: Kuba
* nincs CORS

### LaunchPad.net

* https://LaunchPad.net/
* fiók: Ubuntu One
* REST API funkciók: projekt menedzsment, hibajegy kezelés
  * https://help.launchpad.net/API/Hacking
* Bazaar, Git
* cenzúrázatlan: Kuba
* nincs API CORS

### Pagure.io

* https://Pagure.io/
* fiók: Fedora FAS
* REST API funkciók: projekt menedzsment, PR és hibajegy kezelés
  * https://src.fedoraproject.org/api
* cenzúrázatlan: Kuba
* nincs API CORS

### SourceForge.net

* https://sourceforge.net/
  * forrás: https://allura.apache.org/
* REST API funkciók: hibajegyek, üzenetek, wiki oldal és blogbejegyzés
  * https://forge-allura.apache.org/docs/getting_started/administration.html#public-api-documentation
* cenzúrázva: Kuba
* van API CORS

### Debian Salsa GitLab

* engedélyezve az összes GitLab szolgáltatás, beleértve a CI/CD
  * van API CORS
* van Pages (https://*.pages.debian.net/)
  * van CORS
* https://wiki.debian.org/Salsa/Doc#Web_page_hosting
* https://wiki.debian.org/Salsa/FAQ#How_can_I_use_salsa.debian.org_without_JavaScript.3F

> What can be hosted on salsa? The answer is simple: As long as it is opensource and/or can be included in Debian, it is fine to use salsa. If in doubt, ask.

## Új, kis szereplők

### ChiselApp.com

* https://chiselapp.com/
* Fossil SCM

### CodebaseHQ

* https://www.codebasehq.com/pricing
* git, subversion, mercurial
* 100MB tárhely
* 2 felhasználó
* 1 projekt

### codeberg.org

* 2019
* motorja: gitea
  * nincs API CORS
* feldolgozás nélküli statikus webkiszolgálás (Gitea Pages) *.codeberg.page
  * nics Pages CORS, nincs RSS CORS
* helyszín: Németország
* cenzúrázatlan: Kuba
* CI/CD kutatás alatt
  * Woodpecker CI - Drone.io fork
  * https://codeberg.org/Codeberg-CI/request-access

### cryto.net

* https://git.cryto.net/
* motorja Gitea
* pages nincs engedélyezve
* nincs API CORS

### Gitea.com

* 2019
* motorja: gitea
* helyszín: Kína
* wiki
* gazdag REST API funkciók: projekt menedzsment, hibajegyek, változáscsomagok, fájlok létrehozása
  * https://docs.gitea.io/en-us/api-usage/
* cenzúrázatlan: Kuba
* van API CORS

### GitNet.fr

* https://gitnet.fr/
* motorja Gitea
  * nincs API CORS
* van statikus HTML pages: https://gitnet.page/
  * nincs pages CORS

### NotABug.org

* motorja: Gogs https://gogs.io/
* https://notabug.org/hp/gogs
* helyszín: Németország
* a REST API csak olvasni tud fájlokat, ezt leszámítva teljes értékű
  * https://github.com/gogs/docs-api
  * nincs API CORS
* cenzúrázatlan: Kuba

### GitGud

* https://gitgud.io/users/sign_in
* GitLab
* kérés után osztott CI futtató
* API főleg kiadások kapcsán
  * https://osdn.net/projects/osdn-codes/wiki/CommandLineInterface
* van CORS

### gittea.dev

* https://gittea.dev/
* Gitea
* nincs API CORS

### gogs

* a kérdés, hogy a NotAbug.org frissítette-e a forkját, vagy a régit használja
* gazdag REST API funkciók (2022 óta fájl írással)
  * https://github.com/gogs/docs-api
  * https://github.com/gogs/gogs/pull/7114
  * nincs API CORS és az API csak belépes után hívható

### git.mills.io

* https://git.mills.io/
* Gitea
* nincs API CORS

### OSDN

* https://osdn.net/
* Git, Subversion, Mercurial

### perforce

* https://www.perforce.com/products/helix-teamhub/pricing
* 1GB tárhely
* Git, SVN, Mercurial

### PlasticSCM

* https://www.plasticscm.com/pricing
* 5GB tárhely

### RocketGit

* https://rocketgit.com/op/pricing
* korlátlan
* API csak metaadatok olvasására
  * https://rocketgit.com/op/doc/api
* van API CORS

## Korlátozott tagsággal

A regisztrációkat tipikusan egyenként hagyják jóvá az üzemeltetők.

### blesmrt.net

* https://gitea.blesmrt.net/
* Gitea
* Csehország
* felület: cseh
* nincs API CORS

### git.disroot.org

* Amszterdam
* Gitea
* nincs API CORS

### git.envs.net

* https://git.envs.net/
* Gitea
* nincs API CORS

### framagit.org

* Franciaország
* GitLab
* van API CORS

### libregit.org

* jelenleg csak meghívóval lehet csatlakozni

### RocketNine.space

* https://code.rocketnine.space/
* Gitea
* nincs API CORS

### SourceHut.org

* motorja: Sourcehut
* CI/CD
  * https://man.sr.ht/builds.sr.ht/compatibility.md
* az API csak webhook és felhasználói beállításokra használható
  * https://man.sr.ht/api-conventions.md
* később fizetősnek tervezik

### tildegit.org

* https://tildegit.org/
* Gitea
* nincs API CORS
* van statikus pages
  * https://tildepages.org/
  * nincs pages CORS

## Negatív példák

### GitHub.com

* https://github.com/
* gazdag az API-ja
  * https://docs.github.com/en/free-pro-team@latest/rest
  * van API CORS
* CI/CD: GitHub Actions
  * https://github.com/features/actions
* statikus webkiszolgálás
* nem magunk által üzemeltethető
* üzemeltető: Microsoft
* cenzúrázatlan: Kuba

### BitBucket

* https://bitbucket.org/
* gazdag az API-ja
  * https://developer.atlassian.com/server/bitbucket/reference/rest-api/
  * van API CORS
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
