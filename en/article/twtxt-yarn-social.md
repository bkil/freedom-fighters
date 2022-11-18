# twtxt federated microblogging

## Overview

* User feeds are stored in a line-oriented, timestamped textual file
* Metadata in comments at the top
* A user hosts it on normal static web hosting
* User mentions based on full URL
* https://github.com/buckket/twtxt
* https://yarn.social/about.html

## Aim

* Solve the most common real world use cases that The Fediverse serves: interaction with followers, tags, forum groups
* Retain worldwide potential for scalability
* Pull-based to remain compatible with static web hosting
* Improve barrier to entry by being more inclusive about the type, cost and specification of the devices and services that can participate
* Remain similarly minimalist as Gemini: a well versed developer should be able to implement a full featured client (or server) on a single weekend
* [../server/backend-optional-web-apps.md](../server/backend-optional-web-apps.md)

### Client compatibility

Compatibility should be checked against all maintained or packaged clients.

Threaded:

* https://yarn.social/
* https://www.uninformativ.de/git/jenny
* https://github.com/jdtron/twet
* https://git.isobeef.org/lyse/tt

No threading:

* https://hub.darcs.net/dertuxmalwieder/twtxtc/changes
* https://github.com/deadblackclover/twtxt-el/commits/master
* https://github.com/buckket/twtxt/
* https://github.com/andinus/pyxis
* https://github.com/raspbeguy/twt-tools
* https://github.com/CipherDogs/twtvk-app
* https://github.com/neauoire/twtxtc
* https://github.com/AAorris/hallway
* https://github.com/Luqaska/twtxtExplorer
* https://github.com/hxii/picoblog
* https://gitlab.com/dbohdan/twtxt.tcl

Abandoned:

* https://github.com/rustwtxt/rustwtxt

References:

* https://github.com/topics/twtxt-client
* https://github.com/topics/twtxt
* https://github.com/buckket/twtxt#user-content-contributions

## Client suggestions

### Inline attachments

* "data: URI" could be allowed to share tiny (few kB) GIF/SVG images or binaries

### Expiration

* Applicable to a "forum" that is ephemeral in modality (chat group, room, channel)
* For real time chat use cases (IRC, XMPP MUC), messages outside the event horizon of usual net splits or interruptions due to traveling is around a few hours
* For catch-up type of ephemeral chat (XMPP MAM, Matrix), messages can be read across time zones and over weekends, so they should be kept for a few days or up to a week
* If we don't need to support reading chat history before joining, participants may leave out any message from their feed that had received a #read_receipt from every other participant
* It is not important whether it is removed in a timely manner or not.

### gemini interface

* A twtxt client for viewing feeds and interacting with content
* Accessible over a gemini client
* Server side rendered, possibly running on localhost

### gemini follower discovery

* https://dev.twtxt.net/doc/useragentextension.html
* The viewer could submit their identity as part of the URL input query

### gopher follower discovery

* https://dev.twtxt.net/doc/useragentextension.html
* The viewer could submit their identity as a search request

### gemini subscription

* https://gemini.circumlunar.space/docs/companion/subscription.gmi

### Friendica addon

* Render our Friendica feed as twtxt
* Ability to follow twtxt feeds in Friendica
* Seamless interactions

### CORS headers

* To allow implementing a web client on a different domain
* twtxt.txt files should be served with permissive CORS headers where configuring this is possible
* Exercise caution against serving authorization on the same API domain for security
* https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS

```
Access-Control-Allow-Origin: *
```

### CORS avoidance

* [./circumvent-cors.md](./circumvent-cors.md)
* To allow implementing a web client on a different domain without having to add headers that our web server should output
* Store a copy of each feed in .css

### Search engine optimization

* Store a copy of each feed in HTML
* Preferably under the main feed URL that others are referring to
* Insert cross-feed links
* Optionally format as a twtxt-HTML polyglot via a preformatted block to minimize storage overhead

### CORS proxy

* To bridge the gap of following feeds not reachable by #cors_headers #cors_avoidance #mirroring
* A server that can proxy an HTTP request and add #cors_headers

### Mapping

* If the URL maps to a path on the same machine, avoid duplication during #mirroring
* If we are in the same LAN, use the private address of the machine instead

### Incremental updates

* Honor HTTP If-Modified-Since
* Lazily only fetch as few archives resulted from #compaction as possible to satisfy a user action
* Where supported, scan backwards (forwards?) in the file with HTTP range requests to only fetch metadata updates and newly appended entries
* Optimize feed for chronologically incremental ordering, but accept appending a few edited older entries at the end
* Allow variable width empty whiteout filler entries so larger feeds may be edited in-place in a bandwidth efficient way

### Instance federation

* Federate with ActivityPub and Yarn.social instances
* Scrape the main instance feed
* Scrape (or where available, follow) tags
* Register a puppet user on each instance of interest to be able to submit comments
* Deduplicate content
* Map as #forums

### Forum federation

* Join a bot to Friendica forums and Hubzilla forum channels
* Post introduction and ask for permission
* Propagate kick & ban
* Map as #forums
* https://github.com/mastodon/mastodon/pull/19059

## Protocol suggestions

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
* Messages are proprietary to their submitter and will get hidden after the member leaves the group (or #feed_deletion ), but the submitter may attribute individual messages to the forum account with a slash command to waive this right. At least a minimal amount of time must pass before allowing this.
* Members have a separate subaccount to store their answers for each forum they participate in
* https://git.mills.io/yarnsocial/yarn/issues/325
* https://git.mills.io/yarnsocial/yarn/issues/344

### Calendar events

* Time, place, description (website, end time)
* Allow confirmed members to comment
* Allow participants and guests to RSVP
* Consider combining with the following features: #forums #aggregated_message_reactions #webhooks #email_mentions

### Poll frequency

* Some use cases call for frequent polling (chat) while others allow for daily or on demand updates (blog)
* If the value would be stored in a separately signed metadata file, could also represent "online status" of sorts (poll within 1 minute vs. poll within 8 hours changing dynamically)
* The poll rate should be adaptive based on the expected time of the next post. This could be extrapolated from the time of day, day of week and the weighted posting rate.
* This setting only applies for humans and software directly making requests on behalf of humans. For crawler preferences, see #clawlers This is also distinct from how the "refresh" property is interpreted both by Yarnd as the follower feed polling interval and yearn-search as a visitation interval.
* https://dev.twtxt.net/doc/metadataextension.html#refresh
* https://git.mills.io/yarnsocial/yarn/issues/427

### Poll quota

* A user may be hosting their feed from metered shared hosting or from home through a metered connection
* Followers should spread their intended polling schedule accordingly
* Could also be enforced on the backend, but not all feeds are served from a backend
* Daily and monthly upper bounds
* Number of HTTP requests
* Volume of data transferred
* Divide by number of followers

### Feed metadata for CORS avoidance

* Timestamp of most recent post
* Timestamp of last update to the feed file
* File size
* To allow #incremental_updates with #cors_avoidance
* `access-control-allow-headers` is prone to failure even when the server can be made CORS-aware

### Crawlers

* Honor /robots.txt (TODO: and potentially the non-standard ./robots.txt ?)
* Introduce feed metadata for declaring robot crawling preferences. This is separate from #poll_frequency #incremental_updates
* Revisiting within 24 hours would be undesirable. If the Yarnd "refresh" property exists, its value must also be considered as a lower bound.
* Set a unique and versioned client identifier within the user agent along with a contact to the robot operator
* Load balance based on #poll_quota #backup_accounts #mirroring
* Honor #feed_deletion #redaction #forked_message_correction
* Run on a separate IP address so it can be blocked
* Support gzip and brotli for HTTP compression
* https://en.wikipedia.org/wiki/Noindex
* https://en.wikipedia.org/wiki/Robots_exclusion_standard
* https://gemini.circumlunar.space/docs/companion/robots.gmi

### Unlisted followers

* Number of followers whose URL we do not publish
* Number of feeds we follow whose URL we do not publish

### Backup accounts

* Represent a single meta-feed with multiple alternative URLs
* A feed could have reciprocal mirrors (see #mirroring )
* Introduce a new metadata field to mark which ones are considered master copies (which ones do the author usually push to at the same time) and which are considered replicas (and what is the maximum allowed time lag before declaring each as dead). Failover might also consider #poll_frequency #poll_quota and the monotonic timestamp in #signed_feeds.
* They should be signed with the same key
* Resolve HTTP 301 redirects and memorize new target implicitly
* If somebody follows one of the account URLs, they should follow all of them together
* If access is lost to some of them (either write-access or read as well), the meta-feed could still live on, the live mirrors should delist the dead mirrors and followers should unfollow the dead mirrors eventually.
* Rewrite mentions within our past posted messages upon changes to the main account of who we mentioned via #forked_message_correction
* https://dev.twtxt.net/doc/metadataextension.html#url
* See nomadic identities in ActivityPub:
* https://codeberg.org/streams/streams/src/branch/dev/FEDERATION.md

### Mirroring

* Option to publicly follow a user in a way so that we also republish their #signed_feed
* A feed would also list within its metadata those who mirror it
* May also list the usually observed lag or the most recent update of each
* Can be used when the origin is down, slow, in a load balanced fashion or if nearing its #poll_quota
* Enables those on the same host or LAN to share feeds to lower costs
* Reshare a feed with greater accessibility for #cors_avoidance - i.e., with CORS headers or CSS encapsulation as a workaround

### High availability bots

* Similar to #mirroring but the stream is generated in parallel by multiple users
* The should eventually reproduce the exact same feed independently (minus the update date)
* The should advertise their mutual trust and their independent keys similar to a #backup_account
* This is equivalent power to being admin or moderator within #forums
* Could be used by client side bridges

### Alternate feed links

Use case:

* A user may publish their feed in a subset of formats: with or without CORS, twtxt.txt, Atom, CSS, JSON, prerendered HTML, txt in HTML
* It might be feasible to host them under the same path with different file extensions
* Users may also be #mirroring feeds of other users
* Update the set of references everywhere after one is migrating between #backup_accounts via #forked_message_correction

Mechanism:

* When referring to a feed within a post, it would aid compatibility and efficiency if we shared all existing alternate formats
* The client could choose one supported alternative and only fetch from that one (if it is up to date), not from all redundant versions
* The client could save multiple round trips of indirection, checking for CORS and existence of alternatives
* The mapping could be done inline or via metadata at the beginning of the feed file
* See also #cors_headers #cors_avoidance #search_engine_optimization #mapping

### Alias mention

* Declare the nickname along the URL of our followers or who we follow in the metadata
* A new metadata field could be introduced to share the nickname we use for other feeds we communicate with otherwise
* Mentions could be shortened to @nickname instead of @<nickname feedurl> that is more realistic to type by hand
* Take care to update the metadata on changes to our followings and ensure uniqueness
* Rewrite our past posted messages upon changes via #forked_message_correction
* Canonicalize mentions in incoming posts by expanding the URL

### Feed deletion

* A new metadata field should signal a grace period
* The user should have an option to discontinue all of their publishing activities, deleting all of their former posts
* Should propagate to all of #backup_accounts #mirroring #threads #indexing #forums #forum_federation #instance_federation
* Could possibly include a dead man's switch, such as assume #feed_deletion on the remote side after 366 days of inactivity
* Consider whether all comments could have #expiration by default, such as 30 days

### Signed feed

* To allow #mirroring
* The poster should cryptographically sign their whole feed
* Followers may exercise trust on first use
* Followers should exercise certificate pinning
* Add further metadata fields to declare the minimal amount of time to enforce signature verification
* https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security
* To facilitate redacting messages by mirrors, the poster may separately sign the set of message signatures in case of #signed_messages or just the set of timestamps if they are unique as in #federated_message_identifiers , otherwise just the message hashes
* The feed should include a monotonic timestamp that is signed separately and updated regularly to declare that "no messages were created since the last message up to this time instant"
* https://github.com/buckket/twtxt/issues/122

### Signed messages

* https://git.mills.io/yarnsocial/yarn/issues/770
* May allow for feed aggregating services such as trustless decentralized #forums via #mirroring
* The poster could cryptographically sign individual messages
* May include a monotonic message counter to better inform about skipped messages
* A message may be signed along with the hash of its predecessor if forming a blockchain is desirable
* https://git.mills.io/tkanos/twtxt-encrypted-communication-proposal
* https://w3c.github.io/vc-data-integrity/

### Compaction

* https://dev.twtxt.net/doc/archivefeedsextension.html
* A publishing platform use case (personal blog, knowledge base forum) assumes that you wish to make your content available indefinitely (or until #redaction )
* We would like to reduce bandwidth requirement of syncing long timelines
* Older messages should be archived either in fixed time frames (annually, monthly) or based on an order of magnitude of volume (like about 1000 messages or 100kB) and paged
* The archive links should be marked up with bounding timestamps to allow ID based partial lookups
* Potentially store the archive links as a separate file or as a tree if there would be too many (>16)
* The feed with the most recent posts should be as short as possible and potentially pruned by the #read_receipt of our followers for chat use cases

### Read receipt

* Publish a feed with a list of IDs of the most recent messages within each followed feed that the client of the user has received
* This should also be evident from the User-Agent HTTP request header, but it is not available on all deployments
* See also #poll_frequency #gemini_follower_discovery #gopher_follower_discovery

### Federated message identifiers

* We should be able to reference any single message (for threaded replies, #redaction #read_receipt #forked_message_correction #message_correction_suggestion )
* Could be conveniently a URL
* Must include the full main URL of the feed
* Should include a timestamp that guarantees uniqueness. Seconds accuracy should be sufficient for all real world use cases, but nanoseconds is commonly supported as well.
* May include a cryptographic signature generated from the message and its metadata if tamper-resistance is required in the given use case
* The existing hash extension requires that a server keeps (an index of) all messages in the world (or at least within the intersecting followership circles) loaded in memory or poll a remote backend. This poses a barrier to scaling.
* https://dev.twtxt.net/doc/twthashextension.html
* https://git.mills.io/yarnsocial/yarn/issues/327
* https://git.mills.io/yarnsocial/yarn/issues/42

### Threads

* To aid decentralized discovery and to opt into viewing the full context
* A reply should include the #federated_message_idedentifiers of its parent that defines the subthread (similar to `In-Reply-To` in email)
* Each user who comments on a given thread should start to mirror all #federated_message_identifiers of messages within that thread up to the root (somewhat similar to `References` in email)
* Don't mirror obsolete ones affected by #redaction or #forked_message_correction
* Don't mirror message content in order to respect privacy
* Allow a commenter editing their comment to fork off a question to a new disjoint thread or to position the reply under another, more on-topic thread via #forked_message_correction and others can suggest the same via #message_correction_suggestion
* TODO: For mass scaling, it might be desirable to only list the URLs of accounts of all commenters or if this is still massive, provide for handling as #forums and listing the URLs of trusted #mirroring nodes. Note that such a scale is actually a degenerate use for threading in the real world, but consider whether unifying #threads and #forums would be a feasible workaround.
* https://dev.twtxt.net/doc/twtsubjectextension.html
* https://en.wikipedia.org/wiki/Conversation_threading

To represent the two separate types of message links, we could either overload the hashtag URL to link to the thread root, or the message text could include the other composite ID as free text. Both would allow for grep'ping for threads without having to walk through possibly incomplete reply chains. The twtxt mention and twtxt subject would be used to link direct replies together in a clickable way, while the ID at the beginning of the text would help connect the whole topic together (i.e., to the ID of the root status). A dedicated client would hide it from the interface, while it still wouldn't look terrible from a legacy client. Especially for a simple, flat thread where it would be omitted completely. It would be symmetrical with the original subject this way, but we might consider putting it at the end for legibility. Here's a 4 line example:

```
joke: 2022-10-31T06:54Z\tWhy do programmers confuse Halloween with Christmas?
lola: 2022-10-31T11:11Z\t@<http://example.com/joke> (2022-10-31T06:54Z) Something related to eight?
kids: 2022-10-31T22:22Z\t@<http://example.com/joke> (2022-10-31T06:54Z) Beats me
joke: 2022-10-31T23:00Z\t@<http://example.com/lola> (2022-10-31T11:11Z) @<http://example.com/joke> (2022-10-31T06:54Z) Spot on! Oct 31 = Dec 25
```

Separating these two links allows for the user or moderator to either reply to a specific comment within the topic or to break out a related conversation to a new topic and linking the two together via designating a topic starter.

### Public vs. follower-only threads

* A user could decide whether the content of the reply they submit could be mirrored within the feeds of the #threads and #forums that it targets, or if only #federated_message_identifiers can be published.
* This trades off potential further privacy guarantees vs. opportunities for lowering the request count when displaying threads

### Redaction

* Possibility to hide a past message either recent or archived
* Insert a redaction by referencing #federated_message_identifiers
* Remove from the feed files.
* The timestamp itself might be preserved without the message content to maintain stable #federated_message_identifiers along with the optional signature if using #signed_messages
* A person can redact either their own message or a message from #forums where they are a moderator

### Forked message correction

* Possibility to reply to your own (misspelled) message in a relation that would hide or strike through the old one and show the corrected content instead.
* Both previous replies to the old message and new ones should be linked to the new one, but in a way so that it would be obvious that they were in reaction to different text (click to reveal, etc.).
* https://git.mills.io/yarnsocial/yarn/issues/327
* https://git.mills.io/yarnsocial/yarn/issues/517

### Message correction suggestion

* Allow editing the posts of other users
* Broadcast a suggested rewording or #redaction for the author
* They could accept it to be applied through #forked_message_correction
* After the edit is applied, the edit suggestion could be removed
* The suggestion may come from outside the followers of the author through either forwarding (unreviewed) or a vow (review) by shared contacts (or via moderators in case of #forums )

### Aggregated message reactions

* https://git.mills.io/yarnsocial/yarn/issues/169
* Typically used for Unicode emoji
* At a minimum: like and dislike
* To ease requirements, perhaps impose limits on the timeframe during which one can react, for example within 24 hours (after which you have to reply and place further reactions on the reply)

### Webhooks

* https://github.com/buckket/twtxt/issues/109
* https://git.mills.io/yarnsocial/yarn/issues/91
* For mentions of people who we don't follow
* Either a dedicated real time, self-hosted endpoint
* Or one or more registries used by us along with multiple people
* A registry would then store and forward these mentions later by other private means: webhook, email, XMPP, etc. or each user may poll the registry
* Might consider also using the User-Agent HTTP request header for this where supported

### Email mentions

* If somebody is not following us
* Or if we have not received a #read_receipt from them for a long time (24 hours?)
* They can broadcast their email address in the metadata
* We can send an email to them to notify about the mention (follow request)

### Content indexing

* To facilitate search
* Publish reverse word indexes of the "best" search words, phrases and tags present in our feeds
* To improve results for composite queries, also consider to accumulate each thread and also index it as a meta-entity
* Sign
* Also a good candidate for #mirroring

### Gossip feed index

* A feed may consent to participating in semi-global #content_indexing
* A user may include hashtags or key-value pairs in their feed to facilitate discovery
* The consent must be considered expired after a few months of inactivity to protect privacy and right to be forgotten
* All such metadata including its update date should be signed by the author
* Propagating clients should share the index of consenting feeds ever seen among each other via a dedicated file.
* If a feed fails to be fetched, propagating clients may sign its entry with mentioning the date of the first failing fetch after the most successful fetch and the number of unique days of failure. This should provide testimony for deleting the feed from the index more rapidly.
* Propagating clients may prune the index to honor their storage quota. They may use heuristics of maximizing reach or utility within the network.

### Feed discovery

* A client should offer to search for and follow a limited set of feeds initially after installation to seed federation. This may be either a manually curated list (either feeds moderately and diversely connected or ones providing content catering to a new joiner from the target audience), computed by crawlers based on semi-global statistics or just republishing the #gossip_feed_index of a given user (e.g., of the developer)
* The client may locally store a private ephemeral index of all feeds ever mentioned, possibly along with context, statistics and metadata of each occurrence, similarly to a search engine crawler
* The client may make recommendations about feeds to follow based on its private index and the #gossip_feed_index

### HTML formatting

* Instead of storing markdown and requiring the newline extension
* Store the supported rich text formatting subset with HTML markup
* https://git.mills.io/yarnsocial/yarn/issues/755
* https://git.mills.io/yarnsocial/yarn/issues/846
* https://git.mills.io/yarnsocial/yarn/issues/215#issuecomment-3074
* https://git.mills.io/yarnsocial/yarn/pulls/166#issuecomment-3783
* https://dbohdan.com/wiki/twtxt-line-breaks

### Abuser lists

* https://git.mills.io/yarnsocial/yarn/issues/344
* Any user may share a file where they share their recommendations for "censorship"
* Abusive feed URLs
* Hashes of email addresses for abusive accounts
* Regexp content filters for abusive content
* Lists of IDs for concrete abusive posts - effectively #redaction
* The client could subscribe to any number of such lists
* The client would have a default subscription after installation to one recommended by the software developer
* The follow requests of listed accounts and content matching the filters would be hidden
* Might allow for open #forums if paired with #webhooks or #email_mentions
