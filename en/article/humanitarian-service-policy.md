# Humanitarian service policy

## Terms of service

See the [#details](#details) chapter for an explanation.

Mandatory:

* Altruism: openly commit to regularly benefiting others without compensation
* Locality: speak the local language or conduct physical activities in the given country
* Replication: license your content so that others can reuse it
* Accessibility: prepare for disabilities, old hardware, slow connections, privacy minded settings
* Cooperation: stay in touch with the ring manager and your ring peers

Suggested:

* Outreach: communicate with your own community through at least one open platform
* Syndication: enable humans and machines to follow new content
* Offline: allow users with connectivity challenges portable takeouts
* Intermediaries: prefer ethical service providers that treat users well

## Goals

* This is a recipe we propose for starting community web ring services.
* Depending on volunteer moderation resources available, it would be desirable to maintain dozens of separate rings for everyday areas of life to keep it interesting to less technically inclined people.
* Our aim is to honor the primary goals of the project of freedom of intellectual property and fair open competition for service providers.
* Facilitate in producing content that can reduce the digital divide:
* https://github.com/bkil/kisnux

## Details

### Altruism

* We call an act "altruistic" if it is done for the benefit of another and accomplished irrespective of being granted fair compensation (i.e., as a job responsibility), not expecting a favor in exchange, and not being in extended family relations with the beneficiary
* The person or community behind a given member website shall volunteer to achieve altruistic acts regularly
* They should declare the specific kind of activities beforehand and should publish regular updates about their progress

Such volunteering can be interpreted broadly, but here are a few common examples:

* Collecting trash from natural areas
* Planting trees
* Teaching, mentoring
* Preparing, delivering or serving food for the disadvantaged
* Painting trail marks
* Editing OpenStreetMap
* Operating services for others
* Writing, extending or translating material in a knowledge base that many refer to (e.g., Wikipedia)
* Internationalization of software or portals many use
* Producing visual designs for software, portals or outreach material
* Creating, improving, fixing, documenting, supporting or testing software or portals many use
* Acquiring and onboarding new volunteers, producing required material
* Coordinating altruist acts or others partaking in such
* Online community management, moderation, grooming, delegation, bridging
* ... submit your examples to be included here!

### Locality

* If the topic of the ring requires physical presence for action, its position must reside within the country of the ring manager. The language used may include English in this case.
* Otherwise require that the local language must be used on each member website and for the ring description.

### Replication

* You should declare to license the bulk of your content under an established copyleft license on each page
* You should not use digital rights management
* https://en.wikipedia.org/wiki/Creative_Commons
* https://en.wikipedia.org/wiki/Free-software_licence#Definitions

### Accessibility

* Cater to the needs of those living with disabilities: visual impairment, motor impairment, special input devices
* The majority of relevant content should remain legible where any of the following are disabled: JavaScript, CSS, fonts, images, frames & iframe, cookies & storage
* The majority of content should remain legible on FOSS Linux browsers based on Blink, Webkit, Gecko, Goanna, NetSurf, LibWeb and links2
* Client hardware of up to 20 years of age running up to date software should be tolerable - imagine a Pentium 4 with 512MB of RAM running antiX (2023)
* Should not waste precious metered bandwidth and load with tolerable latency on slow networks. Verify compression and caching headers. Test with "Slow 3G" throttling in Chromium DevTools or well-known SEO metrics such as PageSpeed Insights.

### Cooperation

* The operator of the member website must maintain contact with the ring manager and their peers participating in the same ring through a members-only forum that uses open protocols
* Such as a bulletin board, matrix room, XMPP MUC

### Outreach

* The given member website should maintain their community through at least one open platform
* Suggested to use portable federated alternatives
* Such as Fediverse, mailing list, matrix room, XMPP MUC, NNTP, SIP, BBB, Jitsi, bulletin board forum, Mattermost, IRC, etc.
* https://en.wikipedia.org/wiki/Comparison_of_software_and_protocols_for_distributed_social_networking

### Syndication

* Provide an endpoint that can be subscribed to by your readers using standards such as Atom/RSS, iCal/ICS
* Provide endpoints for accessing by third party websites to allow for example federating interactions or aggregating updates
* Technically, this could be achieved in ways, such as JSONP, CSS, CORS for Atom/RSS/iCal/ICS, CORS JSON API
* Provide visible links to such endpoints on all covered pages and where applicable to API docs as well
* Don't block VPN and Tor
* Don't force a CAPTCHA upon readers

### Offline

* You should adapt a build process that makes it easy to incrementally archive and distribute your work for offline use.
* For example, providing so called compressed database dumps and diff in a torrent format is an established solution for this by many wiki
* Depending on your content, you may also consider providing a compressed folder with the HTML source if it can be opened without a web server, a versioned source control repository or a PDF document
* You may ship a dedicated app or utilize Service Workers to offer a user to prefetch and update content when they are connected to the internet and possibly allow users to share such updates locally as a file
* Lacking the above takeout option, allow scraping from a data center for implementing this by a third party

### Intermediaries

* Prefer service providers that are detailed in other notes of this project
* Some of the qualities we are looking for: non-monopolistic, open protocols, FOSS, local, no vendor lock-in, doesn't track users, sustainable
