# Shared hosting

## Sustainability

* It is beneficial if the self-hoster operator, the users and the platform provider are within the same legal jurisdiction
* Using a small platform provider improves potential for competition and may create jobs locally
* It is easier to target a few larger providers than a multitude of small ones

## Efficiency

* Resources of most servers are usually underutilized and see bursts: CPU, RAM, networking
* Overselling reduces costs for average operators
* Lower power consumption
* Less hardware to manufacture and transport
* Less hazardous waste to dispose of at the end of life
* Can afford to upgrade more often, hence deliver higher peak performance
* Fewer deploy sites mean less auxiliary hardware: uninterruptible power supply, air conditioning, cameras, guards
* Fewer deploy sites mean less network uplinks to subscribe to and better IX placement
* [../../hu/leased-line-isp.md](../../hu/leased-line-isp.md)

## Storage content

If the VM provider went rogue or got infiltrated. Hardening:

* [../server/encrypted-vm-storage.md](../server/encrypted-vm-storage.md)

### VM storage theft

* they could duplicate our disk online

### Physical storage theft

* if they covertly break in while nobody is home or if we colocate our hardware at a data center
* they could easily wiretap our storage bus and cables to record, store and transmit data live, perhaps after inducing a few RAID resyncs to go through the whole contents
* they could duplicate our backups
* if the drives are fast enough, induce an outage to remove the drives, duplicate them and reboot

## Memory content

### VM memory theft

* they could duplicate the memory online
* trusted enclaves are advertised to protect against this, but it is usually just a promise

### Physical memory theft

* if they covertly break in while nobody is home or if we colocate our hardware at a data center
* they can case a minute of downtime by freezing the RAM, quickly replacing it with a matching one to reboot, while inserting the frozen one into another machine to read it
* servers started supporting encryption and authenticating of memory contents via the CPU (AMD Zen), but this is mostly a cat & mouse game
* if we are threatened in the first place, the motherboard and CPU should already be equipped with a backdoor
* https://en.wikipedia.org/wiki/Cold_boot_attack
