# Drawbacks

As compared to common freemium services.

## VPS

* Monthly fee
* Administrative maintenance
* Reduced compatibility (against proprietary protocols)

## Dedicated

Additional drawbacks of hosting on self-owned dedicated hardware in a data center:

* Upfront investment
* Cost of electricity

## At home

Additional drawbacks of hosting at home:

* Additional cost for CCTV, UPS, backup generator, ECC RAM
* Low SLA of consumer ISP
* A consumer ISP preferred that you don't share your connection or operate public services at home. You are legally bound via the terms of service, but it is usually not enforced.
* Slowness of transfer on asymmetric ISP uplink
* More difficult to cooperatively manage with another admin
* Lack of a 24/7 armed security guard
* Incentive for entering your home for theft
* Potential pollution of noise and vibration
* Fire hazard
* Prone to get damaged: tripping over wire, tackling it, chewing toy of pet or child, water damage
* Takes expensive floor space: except if placed on top of a drawer, but that introduces a fall hazard

See also:

* https://en.wikipedia.org/wiki/Home_server

## Cheap routers

Additional drawbacks of hosting on cheap routers:

* No CCTV
* No UPS or backup generator
* No ECC RAM
* No plausible RAID: they could be ideally deployed in off-site pairs, though
* Slowness of processing: depending on business logic and encryption
* Slowness of overall transfer if it involves processing or slow I/O
* Additional development costs of reimplementing everything from scratch in a minimized fashion
* The minimized backend usually offers much less features or in a less desirable quality
* More difficult to debug
