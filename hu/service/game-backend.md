# Játékfejlesztőknek backend üzemeltetése

## Bevezetés

Ha a hobbi játékfejlesztő szeretne a jövőben minél szélesebb körök által is kipróbálható többjátékos (akár föderált) játékokat implementálni, nem tudna-e ingyen üzemeltetni backendet ahová a játékosok kliensei csatlakozhatnak?
Ezen játékok egy része nagyjából valós idejű, míg mások lehetnek késleltetéstűrők, körökre osztottak is.
Kifejleszthető egy játék úgy is, hogy nagyrészt P2P módon végezze a számításait és a kommunikációt (<https://unhosted.org/>).

### Minimális követelmények

- Webes kiszolgálás
  - statikus webalkalmazásnál HTML frontend
  - egyébként letölthető telepítőcsomagok
  - dokumentáció
- Tartós felhasználói tár: például ranglista, mentések, játékórák, szintlépések
- Tűzfal mögötti játékosok összekötése játéktér szinkronizáció vagy esetleg üzenetküldés okán
- Játékszabály ellenőrzés

### Egyedi szerverként

(Ingyenes) virtuális felhőszerveren:

* https://gitlab.com/bkil/hardware/-/blob/master/doc/hu/free-cloud.md
* [../cheap-server-hosting.md](../cheap-server-hosting.md)
* Sok rendszergazdai tudással és többletfeladattal jár

Ingyenes PaaS webszolgáltatás:

* [../free-paas-dynamic-web-hosting.md](../free-paas-dynamic-web-hosting.md)
* Egy ilyen versenyen lehetőleg a játékra szeretnének koncentrálni, és ha lehet, nem a körítésre amennyiben nulláról kellene a backendet is implementálni.

Bővítményként:

* Néha életszerűtlennek hat, de máskor kézenfekvő: miért ne lehetne egy sakkfórumon sakkozni, egy pókercsoportban pókerezni? Érdemes a világszinten legelterjedtebb keretrendszereket megvizsgálni.

## Föderált rendszerek bővítményeként

- https://github.com/friendica/friendica-addons PHP
- https://framagit.org/hubzilla/addons PHP
- Matrix Synapse plugin/module (lásd mjolnir) Python
- https://wordpress.org/plugins/ PHP
  - https://wordpress.org/plugins/activitypub/
- https://www.drupal.org/docs/contributed-modules PHP
  - https://www.drupal.org/project/activitypub
- https://apps.nextcloud.com/ PHP
  - https://nextcloud.com/blog/category/federation/
  - https://nextcloud.com/federation/

## PHP bővítményként

- https://extensions.joomla.org/
  - https://github.com/joomla/rfc/pull/13
- https://www.mediawiki.org/wiki/Category:Extensions
- https://www.dokuwiki.org/extensions
- https://marketplace.magento.com/extensions.html
- https://addons.prestashop.com/en/2-modules-prestashop
- https://extensions.typo3.org/
  - https://github.com/typoplugins?tab=repositories
- https://www.phpbb.com/extensions/
- https://docs.flarum.org/extend/
  - https://github.com/topics/flarum-extension
  - https://discuss.flarum.org/t/extensions
  - https://extiverse.com/
  - https://freeflarum.com/extensions
- https://moodle.org/plugins/
- https://apps.oscommerce.com/
- https://github.com/e107inc/e107/tree/master/e107_plugins
- https://getgrav.org/downloads/plugins#extras
- https://marketplace.concretecms.com/marketplace/addons
- https://www.opencart.com/index.php?route=marketplace/extension&filter_license=0

## Python bővítményként

- https://wagtail.io/packages/
- https://marketplace.django-cms.org/en/addons/browse/
- https://pypi.org/search/?q=&o=&c=Framework+%3A%3A+Plone
  - https://www.plone.org/download/add-ons

## Perl bővítményként

- https://plugins.movabletype.org/featured/plugins/

## JavaScript bővítményként

- https://community.nodebb.org/category/7/nodebb-plugins
- https://ghost.org/integrations/

## Java bővítményként

- https://marketplace.magnolia-cms.com/all-extensions.html
- https://hub.alfresco.com/t5/alfresco-content-services-add/bd-p/add-ons
  - https://docs.alfresco.com/content-services/6.2/develop/repo-ext-points/

## Ruby bővítményként

- https://github.com/publify/publify/wiki/In-Page-Plugins
- https://guides.alchemy-cms.com/about.html#the-core-modules
- https://www.redmine.org/plugins?page=1

### Discourse bővítményként

* https://github.com/discourse/discourse/blob/main/docs/PLUGINS.md
* https://github.com/discourse/discourse/blob/main/lib/plugin/metadata.rb
* https://github.com/discourse/discourse/tree/main/plugins
* https://www.discourse.org/plugins
* https://meta.discourse.org/c/plugin/22
* https://github.com/topics/discourse-plugin

## Frontend widget

- https://www.mediawiki.org/wiki/Extension:Gadgets
- https://git.sr.ht/~spiral/misskey/tree/main/item/src/docs/en-US/create-plugin.md
  - https://git.sr.ht/~spiral/misskey/tree/main/item/src/docs/en-US/features/widgets.md
- https://element.io/element-matrix-store
  - https://github.com/matrix-org/matrix-react-sdk/blob/develop/docs/widget-layouts.md
  - https://github.com/matrix-org/matrix-react-sdk/tree/78b1f6c0b13efd57031a329a1ac62baba948dad3/src/widgets
  - https://github.com/matrix-org/matrix-react-sdk/blob/78b1f6c0b13efd57031a329a1ac62baba948dad3/docs/jitsi.md
  - https://github.com/matrix-org/matrix-widget-api

### Univerzális frontend

- https://en.wikipedia.org/wiki/Browser_extension
- https://en.wikipedia.org/wiki/Userscript
- https://en.wikipedia.org/wiki/Bookmarklet

### Lehetőségek

- https://en.wikipedia.org/wiki/List_of_content_management_systems
- https://whatcms.org/Tech_Reports
