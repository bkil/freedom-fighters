File, Folder and Disk encryption

This article is still a work in progress.

This article offers no warranty of any kind about the correctness of the information provided. It is meant to be used as a starting point: a collection of links to get you started, giving the reader a general overview about the available software and their use cases.

# Disk encryption

## FDE - Full Disk Encryption

Can encrypt entire drives - including your operating system.

Pros:
- hides your filesystem from people with physical access to your computer (if it is turned off)
  - this includes hiding your sensitive files and software
  - makes it harder (if not impossible) for people with physical access to purposely modify your files to add malware to your computer

Cons:
- losing your password means your data is lost

Options on windows:
- veracrypt
- microsoft bitlocker (windows pro only)

On linux:
- Many distros ship installers with an "encrypt disk" option, which often uses LUKS
- Possible to set up yourself
  - https://wiki.archlinux.org/title/Dm-crypt
  - https://wiki.archlinux.org/title/Dm-crypt/Encrypting_an_entire_system

SSD users should read about TRIM (see the warning in the section plausible deniability).

Known possible attacks:
- Evil Maid attack (https://www.kicksecure.com/wiki/AEM)
- Cold boot attack (https://en.wikipedia.org/wiki/Cold_boot_attack)

## Filesystem level encryption

Fscrypt (https://wiki.archlinux.org/title/Fscrypt) natively supported in ext4, f2fs and ubifs filesystems can provide encryption on the directory level.

Metadata, such as timestamps, sizes and numbers of files are not encrypted.

# Plausible deniability

There are two general ways to do plausible deniability:
- a disk that seemingly only contains random data
- a disk/volume that can be unlocked with 2 different keys

## Headerless encrypted disks

Well encrypted disks will appear seemingly random, when there is no header used.
This cannot be used to boot systems from, so it is only recommended to use for
external HDDs.

Tools that can achieve this:
- plain dm-crypt (GUI through zulucrypt) [1]
  - major drawback: limited portability between applications or between different versions of the same application (see [1])
- veracrypt [1]
  - cross platform
  - does not provide plausible deniability if you use it for system encryption [2]
- truecrypt [1]
  - outdated, use veracrypt instead

WARNING! SSD users need to be aware of this: https://wiki.archlinux.org/title/Dm-crypt/Specialties#Discard/TRIM_support_for_solid_state_drives_(SSD)

## Hidden volumes

Existing volumes that contain a second area of encrypted data at a specific offset.

Tools that can achieve this:
- veracrypt (see [3] and [4])
- plain dm-crypt with an offset (can be set up by zulucrypt [1])
  - recommended to use the FAT filesystem in the preceding part
  - be careful not to add so many files into the preceding part which would corrupt the hidden volume

## Sources

[1] https://raw.githubusercontent.com/mhogomchungu/zuluCrypt/master/docs/zuluCrypt.pdf
[2] https://veracrypt.eu/en/docs/plausible-deniability/
[3] https://veracrypt.eu/en/docs/hidden-volume/
[4] https://veracrypt.eu/en/docs/hidden-operating-system/

# Folder encryption

There are different reasons for why you would want to create an encrypted folder. All of these use cases could point to a different tool to be used.

The different use cases discussed are:

- backups
- sending a folder to a friend
- a sensitive folder
- encrypting files before uploading to a cloud

The different tools available are:

- stacked filesystems
- archives (such as .zip, .7z)
- encrypted volumes

First, the different tools are discussed.

## Stacked filesystems

Stacked filesystems create a folder, which contains the encrypted data. These folders can be mounted through the specific software with a password (and/or keyfile).

Pros:
- Possibility for mounting (which is not the case with archives)
- Can be synchronized to clouds more easily

Cons:
- Leaks more metadata (often: sizes of files, modification time of specific files, some solutions: folder structure)

Good use cases:
- encrypting before uploading to a cloud
- sensitive folders

Tools that can achieve this:
- ecryptfs (https://wiki.archlinux.org/title/ECryptfs)
- gocryptfs (https://nuetzlich.net/gocryptfs/)
- cryfs (https://www.cryfs.org/)
- cryptomator (https://cryptomator.org/)

Which one should you choose?

Other comparisons are available: [1], [2].

Ecryptfs is unsuitable for cloud solutions, because it caches heavily [1]. It is also linux-only.

Gocryptfs and cryptomator have been audited [3], [4].
The audit illustrates some possible attacks against gocryptfs, such as swapping the contents of two files by a malicious cloud provider. A simple test on cryptomator reveals that it may also be vulnerable to such attacks (as of Jan 8 2021).
Gocryptfs also leaks metadata, such as the number of files and their sizes and folder structure. Gocryptfs is CLI first, but has a desktop GUI through sirikali. Cryptomator is GUI first, but has a CLI. Cryptomator has first-party android and iOS apps (might be paid). 

CryFS provides more metadata resistance, such as protecting the folder structure, file count and sizes. however its tooling to recover from bitrot is limited. This is acknowledged in its github repo readme [5]. In the event of power failure when writing data, cryFS filesystems can become corrupt. In theory recovery is possible, but the tools to do so do not exist (yet).

[//]: # (Possible future expansions on this section should include: first hand check of cryptomator against the vulns described in gocryptfs audit when a malicious cloud provider comes into play; exploration of other alternatives, such as securefs; checking the bitrot/corruption resistance of gocryptfs and cryptomator; checking the third party android client of gocryptfs, which was reported to be unstable by some matrix.org users; checking how much metadata leaks through cryfs because of timestamps; getting cryptomator to work on wayland, because it's a java app; also a tutorial on using gocryptfs/cryptomator for non-tech savvy users could be used)

Hence, the final suggestion is to use cryptomator if android/ios support is needed, and choose between gocryptfs and cryptomator if it is not needed.

## Archives

Folders can be compressed into a single file through tools such as zip or 7z. These programs often provide the user the option of password-protecting the archive.

Pros:
- Easy to use UX (just type password when creating and when extracting the archive)
- Software in question often familiar to non-tech savvy users (such as 7zip on windows)
- Can provide resistance to bitrot (some formats such as .rar have this built in, other times multiple programs can be combined to achieve this)

Cons:
- Cannot be mounted
- Not suitable for frequent modification and sync (since the entire archive file is changed if a single file is changed). 

Use cases:
- sending a folder to a friend
- backups with a specific time of creation
- archives containing sensitive data

DO NOT USE .ZIPs FOR SENSITIVE DATA

- Zip 2.0 Legacy encryption is known to be weak [6]
- Some zip software supports AES encryption, but windows does not support it by default [7], so for realiable encryption all parties have to install third party software anyways, which negates the top benefit of zips being integrated into windows
- Zips do not encrypt filenames

7z is better suited for encryption. Windows support is provided by 7zip, linux support by p7zip.

Rars have weird licensing and compression does not work on linux.

Tars by themselves do not provide any encryption, so file encryption tools have to be used.

## Volumes

Large files that contain an entire encrypted filesystem.

Pros:
- leaks less metadata than stacked filesystems.

Use cases:
- a sensitive folder
- backups, archives

LUKS in aes.xts-plain64.512.sha512 mode is recommended for encrypted containers by the kicksecure wiki [8]. You can use zulucrypt to easily set such containers up.

If you understand cryptography, also take a look at https://sockpuppet.org/blog/2014/04/30/you-dont-want-xts/ and please contribute to this guide by telling us what this means for encrypted volumes encryption, relative to using stacked filesystems (which often use authenticated encryption).

## Sources

[1] https://www.cryfs.org/comparison
[2] https://nuetzlich.net/gocryptfs/comparison/
[3] https://defuse.ca/audits/gocryptfs.htm
[4] https://community.cryptomator.org/t/has-there-been-a-security-review-audit-of-cryptomator/44
[5] https://github.com/cryfs/cryfs
[6] https://security.stackexchange.com/questions/35818/are-password-protected-zip-files-secure
[7] https://superuser.com/questions/1255917/do-windows-8-1-or-10-support-aes-256-in-zip-files
[8] https://www.kicksecure.com/wiki/Full_Disk_Encryption#Encrypted_Containers

# File encryption

## Public/private key single-file encryption

Preferred: age (https://github.com/FiloSottile/age)

When PGP public keys are available, PGP.

