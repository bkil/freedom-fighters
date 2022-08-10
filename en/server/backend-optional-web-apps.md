# Developing backend-optional web apps

## Why

If a FOSS web application requires complicated server side processing, its continuous maintenance and operation will be less feasible by forks.

Hosting such a backend also usually incurs a non-negligible server cost.

## Backend categories

When you develop a web application, you could minimize reliance on a backend by choosing one of the following solutions.

### Serverless

It would be the best if your application would be fully peer to peer without requiring any intermediary servers at all.

This is out of scope of this draft.
It can get very complicated and is rarely that beneficial compared to the engineering trade offs.

### Static

This is the the main focus of this document.

You can assume that hosting static web assets over HTTP is so easy, you could do it from a broken phone or a $5 wifi router lying on your shelf.
The risk of being exploited through hosting such content is also considered low.

A great multitude of services are built around providing free web hosting either separately, part of a portfolio or as a side effect of providing a service.

* [../../hu/free-static-web-hosting.md](../../hu/free-static-web-hosting.md)
* [../../hu/free-content-delivery-network.md](../../hu/free-content-delivery-network.md)
* [../../hu/free-paas-dynamic-web-hosting.md](../../hu/free-paas-dynamic-web-hosting.md)
* [../../hu/service/vcs-code-hosting.md](../../hu/service/vcs-code-hosting.md)
* [../../hu/service/free-storage.md](../../hu/service/free-storage.md)
* [../../hu/service/free-shell-account.md](../../hu/service/free-shell-account.md)
* [../../hu/service/free-continuous-integration.md](../../hu/service/free-continuous-integration.md)
* [../../hu/service/paid-web-hosting.md](../../hu/service/paid-web-hosting.md)

### Batch processing

You basically still serve your content as static web pages.
However, you can have an elaborate scheme of continuously update the content, but decoupled from the real time visitor requests.
This may be accomplished by a daily scheduled cron job.

* It introduces a slight elevated security risk if the operation of your update mechanism is influenced by user input even indirectly.
* It reduces your expected attack surface area that you are fencing off real time connections from your processing.
* It aids in damage control that you are running around the same frequency as your backup snapshots.

You can host your web pages either at a static web host and run the updater on a separate host like your router and update it via (S)FTP.
You can also host at a dynamic web hosting provider, but disallow any kind of direct script execution by a visitor.

### Piggybacking

You may run freely as a module on top of some other (FOSS) system.

* [../../hu/service/game-backend.md](../../hu/service/game-backend.md)
* [../article/delay-tolerant-games.md](../article/delay-tolerant-games.md)

### Common off the shelf

You can choose to run or integrate a preexisting backend still be simple, maintained, well known across the community with operational experience, and should be easily self hosted.

Possibly multiple parties may already offer hosting for it.

### Trivialized custom

If nothing else works, you might want to implement a server backend to bridge the gap in certain functionality for your project.

You should still modularize the system so that your system might be composed of the functionality offered by multiple backends, some of which may from a different category.
The ultimate goal here is to write and run as little backend code of your own as feasible.

You may look into microservices for an inspiration, but you don't need to overdo it.

* https://en.wikipedia.org/wiki/Microservice
* https://jamstack.org/what-is-jamstack/

## Examples

* [backend-optional-portal-search.md](backend-optional-portal-search.md)
* https://0data.app/glance/

## References

* https://unhosted.org/
* https://en.wikipedia.org/wiki/Static_web_page
* https://en.wikipedia.org/wiki/Web_template_system#Static_site_generators
* https://en.wikipedia.org/wiki/Shared_web_hosting_service
