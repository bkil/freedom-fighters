# twtxt federated microblogging

## Overview

* User feeds are stored in a line-oriented, timestamped textual file
* Metadata in comments at the top
* A user hosts it on normal static web hosting
* User mentions based on full URL
* https://github.com/buckket/twtxt
* https://yarn.social/about.html

## Aim

* Solve the most common real world use cases that The Fediverse serves: interaction with followers, tags
* Retain worldwide potential for scalability
* Improve barrier to entry by being more inclusive about the type, cost and specification of the devices and services that can participate
* Remain similarly minimalist as Gemini: a well versed developer should be able to implement a full featured client (or server) on a single weekend

## Suggestions

### Subaccounts

* A user could regularly publish content and reply in a few very distinct categories of interest with little expected overlap in followers
* Create a separate publishing feed file per subaccount
* Assume marking each post per subaccount with implicit category (or tag) of its own
* The main account feed of a user should link to their own subaccounts (separate feeds) in the metadata for discovery
* Optimizes bandwidth use and reduces clutter

### Forums

* The account holder creating the main forum account controls participants
* Invite-only or confirmed per message: the account holder may add members manually after direct messaging, ideally by forwarding the message the new member would like to send
* Any member could invite others through a slash command
* At a minimum, a forum file should list its members (who are both followers and who the forum follows)
* List the members who have moderator privilege: ability for message #redaction and removal of users from the forum
* Ideally, a forum should also act as a mirror (see #mirroring section) and for efficiency, it should intersperse messages based on timestamps (i.e., it could be understood to be a bot who reposts content from members)
* Messages are proprietary to their submitter and will get hidden after the member leaves the group, but may attribute individual messages to the holder with a slash command to waive this right
* Members have a separate subaccount to store their answers for each forum they participate in

### Calendar events

* Time, place, description (website, end time)
* Allow confirmed members to comment
* Allow participants and guests to RSVP
* Consider combining these features: forum, aggregated message reactions, webhooks, email mentions

### Poll frequency

* https://dev.twtxt.net/doc/metadataextension.html#refresh
* Some use cases call for frequent polling (chat) while others allow for daily or on demand updates (blog)
* If the value would be stored in a separately signed metadata file, could also represent "online status" of sorts (poll within 1 minute vs. poll within 8 hours changing dynamically)

### Backup accounts

* https://dev.twtxt.net/doc/metadataextension.html#url
* Represent a single meta-feed with multiple alternative URLs
* A feed could have reciprocal mirrors (see #mirroring)
* Introduce a new metadata field to mark which ones are considered master copies (which ones do the author usually push to at the same time) and which are considered replicas (and what is the maximum allowed time lag before declaring each as dead). Failover might also consider #poll_frequency and the monotonic timestamp in #signed_feeds.
* They should be signed with the same key
* Resolve HTTP 301 redirects and memorize new target implicitly
* If somebody follows one of the account URLs, they should follow all of them together
* If access is lost to some of them (either write-access or read as well), the meta-feed could still live on, the live mirrors should delist the dead mirrors and the followers should unfollow the dead mirrors eventually.

### Signed feed

* https://github.com/buckket/twtxt/issues/122
* To allow #mirroring
* The poster should cryptographically sign either their whole feed or individual messages
* The feed should have a stable hash to allow efficient content addressed replication
* The feed should include a monotonic timestamp that is signed separately and updated regularly to declare that "no further messages were created until this time instant"

### Incremental updates

* https://dev.twtxt.net/doc/archivefeedsextension.html
* A publishing platform use case (personal blog, knowledge base forum) assumes that you wish to make your content available indefinitely (or until redacted)
* We would like to reduce bandwidth requirement of syncing long timelines
* Older messages should be archived either in fixed time frames (annually, monthly) or based on an order of magnitude of volume (like about 1000 messages) and paged
* The feed with the most recent posts should be as short as possible and potentially pruned by the #read_receipt of our followers
* Honor HTTP If-Modified-Since

### Read receipt

* https://dev.twtxt.net/doc/useragentextension.html
* Publish a feed with a list of IDs of the most recent messages within each followed feed that the client of the user has received
* This should also be evident from the User-Agent HTTP request header, but it is not available on all platforms

### Redaction

* Possibility to hide a past message either recent or archived
* Insert a redaction by ID
* Remove from the feed files
* A person can redact either their own message or a message from a forum where they are a moderator

### Expiration

* Applicable to a "forum" that is ephemeral in modality (chat group, room, channel)
* For real time chat use cases (IRC, XMPP MUC), messages outside the event horizon of usual net splits or interruptions due to traveling is around a few hours
* For catch-up type of ephemeral chat (XMPP MAM, Matrix), messages can be read across time zones and over weekends, so they should be kept for a few days or up to a week
* If we don't need to support reading logs before joining, participants may leave out any message from their feed that received a #read_receipt from everyone
* It doesn't matter if it isn't redacted in a timely manner.

### Forked message correction

* Possibility to reply to your own (misspelled) message in a relation that would hide or strike through the old one and show the corrected content instead.
* Both previous replies to the old message and new ones should be linked to the new one, but in a way so that it would be obvious that they were in reaction to different text (click to reveal, etc.).

### Aggregated message reactions

* Typically used for Unicode emoji
* At a minimum: like and dislike
* To ease requirements, perhaps impose limits on the timeframe during which one can react, for example within 24 hours (then you have to reply and place new reactions on the reply)

### Mirroring

* Option to publicly follow a user in a way so that we also republish their #signed_feed
* A feed would also list mirrors within its metadata
* May also list the usually observed lag or the most recent update of each

### Mapping

* If the URL maps to a path on the same machine, avoid duplication during #mirroring
* If we are in the same LAN, use the private address of the machine instead

### Webhooks

* https://github.com/buckket/twtxt/issues/109
* For mentions of people who we don't follow
* Either a dedicated real time, self-hosted endpoint
* Or one or more registries used by us along with multiple people
* A registry would then store and forward these mentions later by other private means: webhook, email, XMPP, etc. or each user may poll the registry
* Might consider also using the User-Agent HTTP request header for this where supported

### Email mentions

* If somebody is not following us
* Or if we have not received a read receipt from them for a long time (24 hours?)
* They can broadcast their email address in the metadata
* We can send an email to them to notify about the mention (follow request)

### Indexing

* To facilitate search
* Publish reverse word indexes of the "best" search words, phrases and tags present in our feeds
* Sign
* Also a good candidate for #mirroring

### CORS avoidance

* [./circumvent-cors.md](./circumvent-cors.md)
* To allow implementing a web client on a different domain without having to add headers that our web server outputs
* Store a copy of each feed in .css

### gemini interface

* A twtxt client for viewing feeds and interacting with content
* Accessible over a gemini client
* Server side rendered, possibly running on localhost

### Friendica addon

* Render our Friendica feed as twtxt
* Ability to follow twtxt feeds in Friendica
* Seamless interactions

### HTML formatting

* Instead of storing markdown and requiring the newline extension
* Store the supported rich text formatting subset with HTML markup
