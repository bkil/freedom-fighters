# Shared hosting

## Sustainability

* It is beneficial if the self-hoster operator, the users and the platform provider are within the same legal jurisdiction
* Using a small platform provider improves potential for competition and may create jobs locally
* It is easier to target a few larger providers than a multitude of small ones

## Competition

It is much easier for a small third party or hobbist to set up a shared hosting PaaS and compete in service & support offered than setting up an IaaS where you mostly compete by buying as much floor space and electricity as cheap as possible. You could operate a PaaS hosted from home even (from a business fiber ISP), just redirecting a (sub)domain as appropriate or a reverse proxy at your convenience and switch it around.

Almost all IaaS (except budget NAT/IPv6-only ones) require you to route the full raw IP traffic to their own address and you don't have control about scaling or distributing content over CDN or DDoS protection according to demand.

As you outgrow demand, even tiny countries usually offer at least three open access data centers where you could relocate all or part of your subscribers to a VPS or a dedicated rack.

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
