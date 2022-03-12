# Storage encryption on a VM server

## Overview

Is it worth it to use local encryption in the guest container on remote computation platforms - FaaS (lambda), PaaS, IaaS (VPS)?

### Hiding from our own server

Surely the most secure solution would be if the server never had access to any user data in the first place, as is the case with end to end encryption and client-first applications:

* [backend-optional-web-apps.md](backend-optional-web-apps.md)
* [../article/shared-hosting.md](../article/shared-hosting.md)
* https://en.wikipedia.org/wiki/Cloud_computing_security#Fully_homomorphic_encryption_(FHE)

### Server side processing

It can be advantageous if our server has access to our data:

* to serve public content
* metadata and buffering: ease client exchanges, discovery, detect threats and unwanted content
* costly batch transformations: multimedia editing, conversion
* replicating the whole dataset of users: facilitate filter, join and aggregation of one or more users
* deduplication
* improve battery and network bandwidth efficiency

## Operational practices of host

You can't verify the deployment configuration or human operation security practices.

* swap should be disabled or encrypted
* the VM filesystem image (along with databases) and its backups need to be encrypted
* the keys must be stored at a safe place
* an elaborate routine to unlock volumes upon usage

## Client independent guest encryption

* full disk block device encryption
* FUSE filesystem driver
* general encrypting database or file access driver abstraction

### Computational drawback

* if the host has already set up encryption, the two layers of encryption may waste CPU time

### Data at rest benefits

* If the host drive was not encrypted and is stolen, returned for warranty claims or cloned offline by an adversary
* If the host hypervisor is compromised in a way that allows reading the storage of guests, but not their memory
* If storage is transferred over compromised network elements in a decrypted/reencrypted form (e.g., during replication)

## Scoped encryption

* part of the key material could be provided remotely from the request of a client or a scheduled batch process
* the application can do custom encryption of database records and files individually
* only unencrypt data for the duration of each request
* ideally shard subsets of data of a single user using different encryption keys per scope so that not all requests would need to decrypt all data fields of a user
* only unencrypt subsets of data fields daily: for example contact details for recovery or batch notifications (email, phone), protecting them if exploit is eliminated within 24 hours

### Guest infiltration

* if guest or host experiences non-root infiltration that allows reads circumventing file system or database ACL
* protect data of every other user

### Host administrator infiltration

* if the infiltration allows for patching the application binary or reading arbitrary memory within the guest or the host
* protect data of users who did not log in between executing and eliminating a root exploit and subsets of data of others
