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

### Versatile storage

* GitLab, Gitea, Gogs, MediaWiki, WebDAV, GitHub, BitBucket
* DirectAdmin CMD_FILE_MANAGER (HTM_FILE_MANAGER_EDIT)
* Virtualmin, Vestacp, BlueOnyx, Webmin
* Custom CGI
* Manually export to HTML or twtxt to transfer over SFTP, SCP or git
* https://github.com/BeyondCodeBootcamp/Bliss
* https://www.ietf.org/archive/id/draft-ietf-oauth-browser-based-apps-12.html
* https://www.stackscale.com/blog/popular-web-hosting-control-panels/

### Link preview

* May also trigger based on file extension within a shared bare URI
* Images of GIF, JPEG, WebP or AVIF
* Sandboxed HTML documents in iframe for ASCII graphics in txt, CSS-based diagrams, screenshots, animation or interaction
* SVG possibly also sanitized manually for security
* Sharing certificates or binaries
* https://blog.tomayac.com/2019/12/01/animated-svg-favicons/
* See #trusted_origins #image_dimensions
* https://github.com/w3c/webappsec-permissions-policy/blob/main/features.md
* https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allow
* https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP
* https://microformats.org/wiki/rel-license

### Image dimensions

```
![screenshot](screenshot.png#256x128 title)
![screenshot](screenshot.png title =256x128)
![screenshot](screenshot.png title =256x)
![screenshot](screenshot.png title =x128)
![screenshot](screenshot.png title){width=256 height=128}
![screenshot](screenshot.png title){width=256px height=128px}
![screenshot](screenshot.png title){width="256px" height="128px"}
![screenshot](screenshot.png title){:width=256 height=128}
![screenshot](screenshot.png title){:style="width:256px; height:128px"}
<img src="screenshot.png" alt="screenshot" title="title" width="256" height="128">
```

* https://docs.gitlab.com/ee/user/markdown.html#change-the-image-dimensions
* https://github.com/jgm/commonmark-hs/blob/02603646899f4a0c2acc580e5b5a8818c4e68684/commonmark-extensions/test/attributes.md
* https://gitlab.com/gitlab-org/gitlab/-/blob/1c3f7bdac188a45d819365e76fde2101e0dada6a/lib/banzai/filter/attributes_filter.rb#L19
* https://kramdown.gettalong.org/syntax.html#images
* https://github.com/gettalong/kramdown/blob/0b0a9e072f9a76e59fe2bbafdf343118fb27c3fa/lib/kramdown/parser/kramdown/extensions.rb#L139
* https://github.com/flutter/packages/blob/a75d69cfa82fe9c9cdfc2539d4f23558d3a95afe/packages/flutter_markdown/lib/src/builder.dart#L528
* https://stackoverflow.com/questions/49074666/changing-image-size-in-markdown-on-gitlab/74906593#74906593

### Trusted origins

* The origin of the frontend is trusted, see #origin_funneling
* The origin of our feed is trusted
* The origins of who the user follows are trusted
* Certain well known UGC hosting portals may be considered trusted
* The user should be able to specify a list of additional trusted origins
* Should confirm before #link_preview or external links attempt to navigate to other origins

### Inline attachments

* Option to share #link_preview via `data:` or `javascript:` URI
* Up to a few kilobytes (encoded): prefer up to 1kB, warn above 2kB, error above 8kB
* https://en.wikipedia.org/wiki/Data_URI_scheme

### Origin funneling

* A user may receive deep anchor links from other users on external channels
* Links may point to frontend HTML hosted on different origins
* Browser caching is per-origin
* Improve efficiency by funneling cached content to a stable origin either via an iframe or by redirecting
* Redirecting to a trusted frontend also enables trusted password entry
* A customized bookmarklet to redirect to their "home" frontend and transfer any loaded data from the body through the anchor or an opener-based relay
* An option to migrate between frontends
* The preloader offers redirection upon first opening the given origin so the user may also override the version of the app embedded
* May support staged rollout where users are assigned a periodically rotated delay of updating
* Unless disabled by a parameter, should check for a hotfix version on every anonymous page load
* https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API

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
* Optionally format as a twtxt-HTML polyglot via a preformatted block to minimize storage overhead as per #static_html_rendering

### CORS proxy

* To bridge the gap of following feeds not reachable by #cors_headers #cors_avoidance #mirroring
* A server that can proxy an HTTP request and add #cors_headers

### HTTPS mixed content

* Can be worked around on the client side or via a proxy backend
* The client should retry with HTTP or HTTPS upon failure to fetch: expired certificate vs. mixed content
* [./circumvent-https-mixed-content.md](./circumvent-https-mixed-content.md)

### Mapping

* If the URL maps to a path on the same machine, avoid duplication during #mirroring
* If we are in the same LAN, use the private address of the machine instead

### Incremental updates

* Honor HTTP If-Modified-Since
* Lazily only fetch as few archives resulted from #compaction as possible to satisfy a user action
* Where supported, scan backwards (forwards?) in the file with HTTP range requests to only fetch metadata updates and newly appended entries
* Optimize feed for chronologically incremental ordering (an immutable append-only log), but accept appending a few edited older entries at the end
* Allow variable width empty whiteout filler entries so larger feeds may be edited in-place in a bandwidth efficient way by preserving post offsets
* See #append_only_metadata_updates

### Feed priorization

* First fetch followees who we have mentioned recently
* Then who we have participated in the same threads with recently
* Then who have mentioned us recently
* Then based on most recent post
* We may condense this information into the order of the follow metadata lines

### Instance federation

* Federate with ActivityPub and Yarn.social instances
* Scrape the main instance feed
* Scrape (or where available, follow) tags
* Register a puppet user on each instance of interest to be able to submit comments
* Deduplicate content
* Map as #forums
* https://codeberg.org/fediverse/delightful-activitypub-development/issues/16#issuecomment-758257
* https://gitlab.com/paulkiddle/fedi-inbox
* https://carlschwan.eu/2020/12/29/adding-comments-to-your-static-blog-with-mastodon/
* https://github.com/dariusk/express-activitypub/blob/master/routes/inbox.js
* https://github.com/Kirschn/mastodon.js
* https://notabug.org/halcyon-suite/halcyon

### Forum federation

* Join a bot to Friendica forums and Hubzilla forum channels
* Post introduction and ask for permission
* Propagate kick & ban
* Map as #forums
* Option for a bridged user to take over their puppet account subject to verification via a link in their profile
* Option for a remote moderator to specify whether individual bridged users may opt out or not
* https://github.com/mastodon/mastodon/pull/19059
* https://tilde.news/
* https://lemmy.ml/
* https://a.gup.pe/
* https://midnight.pub/
* https://bearblog.dev/discover/
* https://dev.to/t/go
* https://hashnode.com/n/go
* gemini://station.martinrue.com/
* https://status.cafe/
* https://angel-town.cinni.net/

### Feed health indication

* A user could see the health of each followed feed
* HTTP redirect for #backup_accounts
* HTTP 4xx, 5xx, timeout
* Linter: empty file, obvious syntax errors, parser warnings
* The status could be color coded and the list rearranged to show those in error at the top
* Show the timestamp of the last successful poll of the feed
* Show the timestamp of the most recent post within the feed
* Potentially also order the followed feeds by last update date, least recently updated first

### Yarn hash resolution

* Need to resolve the truncated blake2b hash to #federated_message_identifiers in order to follow conversations
* Based on user mentions within the thread
* Based on intersections of followers of participants (and mentioned users) in the thread
* Query the missing message through the API (after made CORS-aware) on one or more participating yarnd servers
* If #mirroring a feed containing hash references, also publish a modified feed with references resolved
* https://dev.twtxt.net/doc/twthashextension.html

### Thread synthesis

* Certain posts (or certain users) may fail to mention which exact message they are replying to
* In case when the post includes a mention (especially if it starts with a mention), the most recent post of the mentioned user before that point in time could be searched for
* The previous or the next message of the mentioned user may include a thread reference
* Citation may be detected to find a recent message that contains the text
* See #federated_message_identifiers #threads

## Hosted account state

### Color scheme

### Show inline images

As per #link_preview

### Trusted domains

### Followers metadata

* For #feed_priorization
* To enable lazy loading when using multiple devices
* The poll order of our followed feeds
* The desired poll frequency of each feed adapted to the most recent observed activity
* The last poll timestamp
* Per feed metadata mentioned in #feed_metadata_for_cors_avoidance
* Private follows

### Multiple account logins

## Protocol suggestions

### Subaccounts

* A user could regularly publish content and reply in a few very distinct categories of interest with little expected overlap in followers
* Create a separate publishing feed file per subaccount
* Assume marking each post per subaccount with implicit category (or tag) of its own
* The main account feed of a user should link to their own subaccounts (separate feeds) in the metadata for discovery
* Optimizes bandwidth use and reduces clutter

### Forums

* Pseudo-forums of categorical feed bookmark sets where no interaction is required on part of the feed
* Ideally, a forum should also act as a mirror (see #mirroring section) and for efficiency, it should intersperse messages based on timestamps (i.e., it could be understood to be a bot who reposts content from members), potentially served as a registry file
* Messages are proprietary to their submitter and will get hidden after the member leaves the group (or #feed_deletion ), but the submitter may attribute individual messages to the forum account with a slash command to waive this right. At least a minimal amount of time must pass before allowing this.
* Members should create a separate subaccount to store their answers for each forum they participate in
* A member may reuse a single subaccount between strongly related forums to facilitate cross-posting
* A member may indicate that they only wish to broadcast posts that mention the forum user
* A forum may list allowed hashtags and it will only broadcast posts (or roots) containing it
* A forum may indicate that all broadcast posts should be considered to carry a set of hashtags for search engines
* A member may indicate that all their posts broadcast towards the forum should be considered to carry a set of hashtags for search engines
* Sticky post links in metadata about detailed topic and rules
* See also: #forum_access_control #directory
* https://git.mills.io/yarnsocial/yarn/issues/325
* https://git.mills.io/yarnsocial/yarn/issues/344

### Forum access control

* The account holder creating the main forum account controls participants
* The account holder and moderators automatically act upon commands sent by a member: accept, forward, invite, follow
* The account holder and moderators act upon commands sent by a member after reviewing: -accept, [-]acceptlist, -forward, -invite, -follow, [-]ban, [-]banlist, message #redact , #forked_message_correction
* The account holder automatically acts upon commands sent by a moderator: [-]accept, [-]acceptlist, [-]forward, [-]invite, [-]follow, [-]ban, message #redaction , #forked_message_correction
* The account holder acts upon commands sent by a moderator after reviewing: [-]moderator
* At a minimum, a forum file should list its members (who are both followers and who the forum follows)
* List the members who have moderator privilege (implies membership)
* List users who can not be invited either individually or by referring to #abuser_lists (ban)
* List users either individually or by referring to #abuser_lists and #directory whose forward and invite request will be automatically accepted (turned into a forward and invite respectively)
* A member can issue a time limited invite for a specific non-banned user (main feed) through a slash command (implies accept). This is expensive as it involves polling the invited feed for a follow request.
* A member can share #webhooks that include a time-limited token for accepting requests for forward and follow. The member shall review this push channel and issue a forum forward or follow to acceptable requests: #webhooks #email_mentions #uri_query_push
* Forwarded per message: a new, untrusted outsider may just want to ask a question without the forum having to worry about flooding. The message can be delivered through any feed in common with a member or in #webhooks. Each external reply should also be forwarded the same way.

```
# moderator = http://m.example/main/f.txt
# invite = 2022-01-01 http://i.example/main.txt
# follow = http://u.example/main/f.txt
# access = banlist http://m.example/main/b.txt
# access = acceptlist http://m.example/main/a.txt
# access = ban http://*.evil.example/*
# access = accept http://a.example/main.txt
# access = accept http://*.pub.example/*
```

### Calendar events

* Time, place, description (website, end time)
* Allow confirmed members to comment
* Allow participants and guests to RSVP
* Consider combining with the following features: #forums #aggregated_message_reactions #webhooks #email_mentions
* https://aaronparecki.com/2019/12/21/4/indieweb-events
* https://indieweb.org/rsvp#How_to_publish

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
* See #account_slicing
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

* Similar to #mirroring but the stream is generated in parallel by multiple users with possibly different operating schedules
* They should eventually reproduce the exact same feed independently (minus the update date)
* They should advertise their mutual trust and their independent keys similar to a #backup_account
* This is equivalent power to being admin or moderator within #forums
* Could be used by client side bridges
* The accountable bot operator should be specified (`# operator = http://example`)
* See #account_slicing

### Account slicing

* A user must be able to both use the native system and also keep using external accounts on bridged platforms
* Bridges may operate 24/7 and with lower latency than a client
* Exactly one feed among the slices must be a main slice and it must be marked within each feed (`# main = http://example`)
* All slices must be interlinked to signal trust (`# slice = http://example`)
* The main slice may mark any other slice as distrusted (`# unslice = http://example`)
* A user should see posts from all of their slices under a single unified timeline
* A user should not be pinged by their own posts within other slices
* Posts by all slices of a given user should be attributed to the same user account and should be mostly indistinguishable on the interface for others
* Following a feed should follow all sibling slices at the same time
* A user may aggregate and sign posts from all of their slices again to their main slice
* A user should be #mirroring the whole set together
* See #high_availability_bots #backup_accounts

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
* See also #cors_headers #cors_avoidance #search_engine_optimization #mapping #static_html_rendering

### Static HTML rendering

* Alternate content metadata field to link to a HTML/gemini version of the feed (unless a polyglot to begin with as per )
* The HTML version should be accessible though a minimal web client without JavaScript and for #search_engine_optimization
* Posts should be legible, but it need not look perfect
* It may be shown in full fidelity by a dedicated client or web app using progressive enhancement
* Messages and threads should carry unique anchors
* #message_mention and #thread_subtree_mention should be rendered to a URL (e.g. http://example.com/joke/2022.html#%32022-10-31T06:54Z )
* https://indieweb.org/URL_design
* Test with existing data set
* https://github.com/tkanos/we-are-twtxt

### Mention aliases

* Declare the nickname along the URL of our followers or who we follow in the metadata
* A new metadata field could be introduced to share the nickname we use for other feeds we communicate with otherwise
* Mentions could be shortened to @nickname instead of @<nickname feedurl> that is more realistic to type by hand
* Take care to update the metadata on changes to our followings and ensure uniqueness
* Rewrite our past posted messages upon changes via #forked_message_correction
* Canonicalize mentions in incoming posts by expanding the URL and then contracting to our own nick in our own view
* Collect URL of undeclared mentions based on the aliases used by follows of the post parent, of thread ancestors upwards, of any participants of the thread tree or of anyone who we follow

### Append-only metadata updates

* Interpret and generate all metadata in a feed in a way that allows for updates that are offset-preserving and enable append-only following
* For scalar keys, use the last occurrence of the key and undefine the key if set to the empty value
* For multivalued keys (follow, link, mention), if the key is prefixed with minus, undo its effect (e.g., `# -follow = http://test.example` )
* For `link`, use the last occurrence per URL for the description
* For multivalued keys that possess subkey uniqueness semantics (mention), use for the last occurrence per subkey and interpreted an empty value as cancellation
* For `follow`, interpret the special nick of `-` as cancellation (e.g., `# follow = - http://test.example` )
* The effect of a change should only be visible after the modification (e.g., renaming the alias of a follower would not need to rewrite mentions in previous posts)
* Insert the special meta command line of `# reloadFeed = 1` to the exact tail byte offset if in-place modifications were made to the earlier parts of the feed that could not be represented as patches or which resulted in relocation of posts
* If the whole feed could be made append-only, #federated_message_identifiers may be replaced with file offset
* Should state this invariant of feed via `# appendOnly = 1`

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
* Normal publishing feeds should not be pruned so every post maintains permalinks
* Introduce new metadata that points to the next feed after this one is closed and indicate either the most recent update if that one is also closed, or no timestamp (if it is not closed), (e.g., `#next = 2023-01-01T00:00Z http://test.example/2022-12.txt` ).

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

### Message mention

* A syntax through which a post can mention (reference, point towards) one or more messages based on #federated_message_identifiers
* Should ideally produce a ping for the mentioned user with existing parsers

```
@<http://example.com/joker>(2022-10-31T06:54Z)
@<http://example.com/joker#2022-10-31T06:54Z>
@joker(2022-10-31T06:54Z)
```

### Thread subtree mention

* A syntax through which a post can mention (reference, point towards) all messages under the thread subtree based on #federated_message_identifiers
* Might produce a ping for either only the top poster user or everyone within the thread
* see: #threads

```
@<http://example.com/joker>(2022-10-31T06:54Z*)
@<http://example.com/joker#2022-10-31T06:54Z_replies>
@joker(2022-10-31T06:54Z*)
```

### Threads

* To aid decentralized discovery and to opt into viewing the full context
* A reply should include the #federated_message_idedentifiers of its parent that defines the subthread (similar to `In-Reply-To` in email)
* Idea#1: Each user who comments on a given thread should start to mirror all #federated_message_identifiers of messages within that thread up to the root (somewhat similar to `References` in email)
* Idea#2: Each user who comments on a given thread should mirror all #federated_message_identifiers (or at least their feed URL) of siblings and on each level towards the root, all predecessor siblings. This enables resilience against parent redaction.
* Don't mirror obsolete ones affected by #redaction or #forked_message_correction
* Don't mirror message content in order to respect privacy
* A user who comments on the thread may decide to rearrange the thread or hide (via #redaction ) any comment from their followers viewing the thread through their timeline. They will be notified about any alteration.
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
* Help captioning previewable content such as multimedia
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
* A registry would then store and forward these mentions later by other private means: webhook, #uri_query_push , #email_mentions , XMPP, etc. or each user may poll the registry
* Might consider also using the User-Agent HTTP request header for this where supported
* A user must list all of their pending outgoing hooks within their feed to authenticate the request, otherwise it should be disregarded. I.e., in case of a follow request, a counter-follow must already be present.
* See #uri_query_push
* http://superkuh.com/blog/2020-01-10-1.html

### Email mentions

* If somebody is not following us
* Or if we have not received a #read_receipt from them for a long time (24 hours?)
* They can broadcast their email address in the metadata
* We can send an email to them to notify about the mention (follow request)
* See #webhooks

### URI query push

* For clients where setting the HTTP User-Agent request header is not possible
* Allows for follower discovery on static web hosting via analysing the server request log
* Optionally pass in the feed of the reader within the query
* See #webhooks

### Content indexing

* To facilitate search
* Publish reverse word indexes of the "best" search words, phrases and tags present in our feeds
* To improve results for composite queries, also consider to accumulate each thread and also index it as a meta-entity
* Sign
* Also a good candidate for #mirroring

### Sitemap

* Enumerating all public files on our host
* https://en.wikipedia.org/wiki/Sitemaps

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

### Directory

* Anyone may moderate and share a set of feeds
* They should share the criteria for inclusion in the description and include hashtags in the metadata
* Represented just like a #forum except that a timeline should not be rendered from the posts of the followers and none should be mirrored either
* Thus it is permitted to also subscribe to a directory with a main user feed
* Members should hold the directory list they are part of in a different metadata field (`# directory = http://a.example/`)
* A widget can be shown on the user profile for each listed directory with description and links to a previous, next and random profile similarly to webrings in #static_html_rendering
* Membership can also be used for acceptance #abuser_lists
* See also #feed_discovery

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
* Iterative positive & negative globs and regexp for matching a URL
* Hashes of email addresses for abusive accounts
* Regexp content filters for abusive content
* Lists of IDs for concrete abusive posts - effectively #redaction
* The client could subscribe to any number of such lists
* The client would have a default subscription after installation to one recommended by the software developer
* The follow requests of listed accounts and content matching the filters would be hidden
* Might allow for open #forums if paired with #webhooks or #email_mentions
