# Ingyen privát tárhely

## Bevezetés

Ezek közül van amelyiken lehet adott körök számára elérhetővé vagy akár publikussá is tenni egyes entitásokat vagy kollekciókat.
Az ÁSZF-nek fenntarthatóan meg kell engednie a biztonsági mentések tárolását és/vagy nagy bináris, titkosított fájlok átmeneti megosztását szűkebb köröknek is.
Akár átmeneti időre, akár szoftverkiadásokhoz vagy open data készletekhez köthetően tartósabban.

A következők ezt pont tiltják:

* [../free-static-web-hosting.md](../free-static-web-hosting.md)
* [../free-paas-dynamic-web-hosting.md](../free-paas-dynamic-web-hosting.md)
* [paid-web-hosting.md](paid-web-hosting.md)

Ezek nagyjánál nincs ingyen a privát tároló és/vagy a tárolók ilyen hasznosítása atipikus:

* [vcs-code-hosting.md](vcs-code-hosting.md)

Az API elérés olyan használati eseteket tehet lehetővé, mint a világszintű föderált fotógaléria vagy élő gyűjteményes open data adatbázisok elosztott tárolása és felhasználási helyen történő fúziója.

### Szempontok

* A feltöltők és letöltők követése
  * Személyes adatok fúziója egyéb forrásokkal
  * A cég, szoftver és infrastruktúra országa
  * Elérhetőség Tor vagy proxy útján
* Feltöltés vagy letöltés használhatósága JavaScript nélkül
  * CAPTCHA
  * Harmadik fél által hívható publikus, dokumentált HTTP (REST) API
  * FOSS kliens programmal vagy rutinkönyvtárral
* Tartósan beágyazható vagy megosztható közvetlen hivatkozás (pl. curl vagy wget számára)
* Feltöltési feltételek
  * Kínált tárhely mérete
  * Maximális fájlméret
  * Tárolási idő, eléréshez kötött megőrzés
* Letöltési feltételek
  * Letöltés előtt várakoztatás
  * Időszakonkénti lekérési vagy sebességkorlát
  * Hirdetések

## FOSS alternatívák

### Filen.io

* https://filen.io/
  * https://github.com/FilenCloudDienste
* 10GB ingyen tárhely
* zero-knowledge
* böngészős-, asztali- és mobilalkalmazással

## Etikus alternatívák

### Proton Drive

* https://proton.me/drive/free
* 1GB tárhely
* E2EE
* 1 kattintással megosztható linkek
* saját szervereken (nem a felhőben) üzemeltetik

## Kevéssé etikus alternatívák

### Kevésbé etikus VPS

Előnye, hogy olyan protokollt és titkosítást telepítünk rá amilyet szeretnénk. Hátránya, hogy ingyen VPS-t nem tud fenntarthatóan kínálni etikus szereplő.

* https://gitlab.com/bkil/hardware/-/blob/master/doc/hu/free-cloud.md

### 1Fichier

* https://1fichier.com/tarifs.html
* maximális fájlméret 300GB
* vendégként és ingyenes regisztrációval
  * hirdetések
  * CAPTCHA
  * késleltetés
* ingyenes regisztrációval
  * 1 TB tárhely
  * FTP és API feltöltés
  * letöltés nélküli feltöltött fájlok elévülése: 30 nap
  * "inline" (hotlinking?)
* fizetős csomagokban: tartós tárhely, nincs hirdetés, nincs CAPTCHA, nincs késleltetés

### Backblaze B2

* https://www.backblaze.com/b2/cloud-storage-pricing.html
* 10GB tárhely
* 1GB/nap letöltés ingyen
* 2500 lekérés/nap és 2500 listázás/nap ingyen

### Dropbox

* https://www.dropbox.com/basic
* 2GB tárhely

### Keybase Filesystem

* https://en.wikipedia.org/wiki/Keybase#Keybase_Filesystem_(KBFS)
  * https://book.keybase.io/docs/files
* 250GB tárhely
* E2EE titkosítás
* cég: Zoom
* ország: USA

### Storj DCS

* https://www.storj.io/pricing
* 150GB tárhely
* 150GB/hó forgalom
* E2EE titkosítás
* szolgáltató országa: USA (Atlanta, GA)

## TODO: Elemzésre vár

* Google Cloud Storage http://code.google.com/apis/storage/
* Google Drive https://drive.google.com/
* Google Photos
* HDFS
* Hubic
* Jottacloud
* Koofr
* Mail.ru Cloud
* Mega
* Memory
* Microsoft Azure Blob Storage
* Windows Live OneDrive (SkyDrive) https://onedrive.live.com/about/en-gb/
* OpenDrive
* OpenStack Swift Storage https://launchpad.net/swift/
* pCloud
* premiumize.me
* put.io
* QingStor
* Seafile
* SugarSync http://sugarsync.com/
* Tardigrade
* Uptobox
* Yandex Disk 10GB
* Zoho WorkDrive
* Alfresco Cloud http://www.alfresco.com/
* Windows Azure BLOB http://www.microsoft.com/windowsazure/windowsazure/
* Basecamp http://basecamp.com/
* Caringo Swarm https://www.caringo.com/
* Ceph http://ceph.com/
* Cleversafe https://www.cleversafe.com/
* Cloudian http://www.cloudian.com/
* 3GB CloudMe (iCloud) 1GB http://www.cloudme.com/
* CMIS http://docs.oasis-open.org/cmis/CMIS/v1.0/cmis-spec-v1.0.html
* Dell EMC ECS http://www.emc.com/storage/atmos/atmos.htm
* Dell EMC Elastic Cloud Storage https://portal.ecstestdrive.com/
* Dell EMC Isilon https://www.dellemc.com/content/emc/en-ph/storage/isilon/
* Egnyte http://egnyte.com/
* Eucalyptus Walrus http://www.eucalyptus.com/
* Evernote https://evernote.com/
* FilesAnywhere http://www.filesanywhere.com/
* Glasscubes https://www.glasscubes.com/
* Google Docs http://docs.google.com/
* Google Sites http://www.google.com/sites/overview.html
* Hosting Solutions http://www.hostingsolutions.it/
* HP cloud http://hpcloud.com/
* HP Helion http://www8.hp.com/us/en/cloud/helion-overview.html
* HPSS http://www.hpss-collaboration.org/
* Huddle http://huddle.com/
* IBM Bluemix Object Storage https://console.bluemix.net/catalog/services/object-storage
* IBM Cloud Object Storage https://www.ibm.com/marketplace/cloud/object-storage/us/en-us
* IBM Files Cloud http://www-01.ibm.com/software/lotus/products/connections/files.html
* iCloud Drive https://www.apple.com/ios/whats-new/icloud-drive/
* Igneous http://www.igneous.io/
* iKoula https://www.ikeepincloud.com/
* Jive http://www.jivesoftware.com/
* LeoNovus http://www.leonovus.com/
* Memset http://www.memset.com/cloud/storage/
* Minio Object Storage https://www.minio.io/
* Mirantis https://www.mirantis.com/
* MooseFS https://moosefs.com/
* Nasuni https://www.nasuni.com/
* NetApp https://www.netapp.com/
* Microsoft Office 365 http://www.office365.com/
* OpenIO http://openio.io/
* Open S3 - S3 Compatible Cloud http://open.eucalyptus.com/wiki/EucalyptusWalrusInteracting_v1.6
* Oracle
* Quantum https://www.quantum.com/en/products/object-storage/
* Rackspace http://www.rackspace.com/
* Salesforce.com https://www.salesforce.com/
* Scality http://www.scality.com/
* Microsoft SharePoint http://sharepoint.microsoft.com/
* SoftLayer http://www.softlayer.com/
* SwiftStack https://www.swiftstack.com/
* ThinkOn http://thinkon.com/
* Trend Micro http://us.trendmicro.com/us/products/personal/safe-sync/
* Wasabi
* Zimbra http://www.zimbra.com/
* 6GB https://en.wikipedia.org/wiki/Baidu_Cloud
* https://en.wikipedia.org/wiki/Dropmysite
* https://en.wikipedia.org/wiki/ElephantDrive
* 5GB https://en.wikipedia.org/wiki/IDrive_Inc.
* 2GB https://en.wikipedia.org/wiki/Jumpshare
* 10GB https://en.wikipedia.org/wiki/MediaFire
* 7GB https://en.wikipedia.org/wiki/MiMedia
* 10GB https://en.wikipedia.org/wiki/Syncplicity
* 3GB https://en.wikipedia.org/wiki/Tresorit
* 10GB https://en.wikipedia.org/wiki/Attic_(backup_software)#Borg
* 100MB https://en.wikipedia.org/wiki/SecureSafe
* 10GB https://em.wikipedia.org/wiki/Tencent_Weiyun
* általános szolgáltatók: FTP, SFTP, HTTP, WebDAV

## Nem ingyenes

### Amazon AWS

* https://aws.amazon.com/free/free-tier/
* _Nem világos, hogy lehet-e használni kívülről fizetős VM és átviteli felárak nélkül (TODO: esetleg AWS Lambda segítségével?)_
* 25GB Amazon DynamoDB
* 10GB Amazon Glacier (API)

### Amazon Drive

Jelenleg Magyarországon nem ingyenes. Amazon Prime előfizetés és Kindle Fire mellé is jár.

* https://en.wikipedia.org/wiki/Amazon_Drive#Free_5GB

### ExpanDrive

* https://www.expandrive.com/desktop/buy/

## Csak próbaidőre

### Amazon S3

* 5GB tárhely
* Amazon S3 (+ EC2/EBS VM block storage)
* 12 hónap próbaidő

### Box

* https://www.box.com/en-gb/pricing
  * korábbi nevén: Box.net
* 100GB tárhely
* 14 nap próbaidő

### Citrix ShareFile

* https://www.sharefile.com/pricing
* max. 100GB fájlméret
* korlátlan tárhely
* 30 nap próbaidő

### Enterprise File Fabric

* https://eu.storagemadeeasy.com/pricing/
* 14 nap próbaidő bankkártya nélkül
* 20GB tárhely

## Hivatkozások

* https://rclone.org/overview/
* https://eu.storagemadeeasy.com/cloud_list/
* https://en.wikipedia.org/wiki/Comparison_of_online_backup_services
* https://en.wikipedia.org/wiki/Comparison_of_file_hosting_services
* https://eylenburg.github.io/cloud_comparison.htm
