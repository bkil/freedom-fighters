# Reconstructing topic threads from linear chat

## Goal

Construct a discussion medium for a given community that can be accessed casually and comfortable on as many interfaces as possible.

### Interfaces

* email mailing list
  * unlimited via unfederated localhost POP3/IMAP
  * limited amount directly towards external servers
  * a bit high limit if opting in to hierarchical forwarding
* not preferred: IRC
* Matrix
* XMPP MUC
* FluxBB
* Discourse
* Friendica (posts to personal circles, forums, event calendar)
* issue tracker: GitHub, GitLab, (BitBucket?)
* domain specific: OSM changeset comments, OSM diary, OSM map notes, Wordpress
* mediawiki "Talk pages" for both articles and personal space
* eventing systems: Meetup.com, GetTogether.community, Mobilizon, mediawiki attendance list, Facebook (probably one way anonymous)

### Features

* Internationalization
* Ability to deploy on free hosting (via PHP or Haxe)
  * Option to piggyback the backend on some widespread server, similarly to [../service/game-backend.md](../service/game-backend.md).
  * Option to avoid reaching quotas, like email send/receive limits
* Federated credentials
  * Multiple admins may run this same system concurrently where they might share the responsibility and/or load balance receiving or sending messages to interfaces.
  * Some of the admins or users may have elevated privileges on some of the platforms that they would like to share with a trusted peer group (or their personal circle of trust).
    * e.g.: Meetup.com, GetTogether.community event updates (Facebook?)
* Users may desire to map their own personal identities between the interfaces if they had registered accounts on more than one.

## Implementation

### Forwarding order

Forward newly posted messages in the following order:
* Immediately: mutable real time interfaces
* After 5 min: if the poster is a trusted peer and passing basic sanity checking (check for accidental copy&paste, spam, etc.)
* After 10 min: if the poster is a trusted peer
* After 15 min: if passes basic sanity checking
* After 1h: if it has a reply from a moderator
* After 2h: if it has a reply from a trusted peer
* After 24h: all unmoderated messages

### Sequential transmission

* Ideally where possible, messages should not be broadcast to a whole group at the same time, but sequentially in a well computed order in order to allow time for trusted peers to hide messages from others on both mutable and immutable interfaces before moderators could take action.
* Randomized
* Weighted by expected time to click `report abuse` button (correlated with time of day, day of week, general and recent read receipts and replies)
* Weighted so that everyone (practically the most active members) should have to read and report the same amount of abuse on the long run

### Indicators of same thread

How do we reconstruct threads, given that one posts on a linearized interface (Matrix, XMPP)?

#### Reply button

E.g. in Matrix or XMPP 

#### Citing part of a previous message

* At least a few words (based on word rarity)
* Within blockquote, code, italic, quotation marks
* Within free text (based on a single, very rare word or a few in the same message or consecutive messages from a recent message)

#### Mentioning users

* @-mentioning a user who commented recently on the same thread (or a parent thread of a subthread)
* Within 1-2 days
* Within a much longer time span if not many conversation had taken place since then
  * If only a few recent messages - less than a few pageful.
  * If only a few clusters of discussions - possibly a few more pages, but happening only around 1-2 points in time (e.g., cluster within 1h of the previous message).

#### Read receipt

* If the most recent message is not very old, considering the room traffic (1-2 day old?)
* If the most recent message was not read by many (compared to the usual count after 1 week)
* If the read receipt and/or typing indicator of this poster is recent
  * e.g., within 10 minutes
  * more for a longer reply
  * more if based on the past read receipt, the poster had to read a lot of previous messages before posting

#### Time

* Keep track of recent activity in the room to try to detect whether multiple topics are open and being discussed simultaneously
* Keep statistics about how many new topics are opened in a given room per week
* Within 10 minutes of the last message if multiple topics are discussed
* Within 1h if a single topic seems to be discussed
* Within 1h if the most recent message is mine
* Reconstruct the time of day activity of the participants and evaluate whether the most recent message was posted when most were not active.

#### Content heuristics

Allow for more slack if the message does not contain:

* a question mark
* a URL
* media attachment

#### Aggregation

* Delay messages for a bit more time (5-10 minutes, depending on typing indicators and poster statistics?).
* Attempt to interpret and even forward such messages in a single batch (for interface that prefer longer posts, like Friendica, FluxBB, Discourse).

#### Combinations

* One can click the `reply` button on an earlier message or mention one by name, and then type in some more messages afterwards.
* Consider whether these messages are part of the same thread/reply and aggregate them as needed.

#### Interaction

* The bot should place a reaction on a given message if it is not sure about its thread.
* For example, it could offer numerical choices for IRC (perhaps via a private message), and clickable reactji over Matrix.
* Choices:
  1. new topic
  2. continuation of my last message
  3. reply to most recent message posted by someone else
  4. reply to someone else, type in name

#### Topic merging

* If at any point we discover that a new topic seems to be the same as a previous one, and hence its context and knowledge would be useful for the inquirer, we should merge the two.
  * Copy/move over all messages to the previous topic and remove the new topic.
* A bot may analyze each message in the topic and look for correlation
  * URL
  * rare words
  * phrases)
* A human may post a URL to the previous topic (on any interface).
  * Approved by a moderator posts this or reacts positively.
  * Or possible type in (a slash command along with) search words so that the bot will find the URL.
* Allow linking topics together later on either via subthreads or for a wiki knowledge base overview

#### Divergence

* Allow separating topics that had either been merged in error or that have diverged organically.
* Reply to the message where to slice with a slash-command and/or reply with reactji to cherry pick the messages to move.
* Optionally link it as a subthread to the parent thread with a slash-command
  * Also place a non-merging URL to reference the parent thread for better context.

#### Topic name generation

* If the first sentence is short enough, use it as is
* Otherwise drop stop words and copy the initial part
* Later: summarize via NLP
* Allow changing it via slash command for the poster or a moderator

## TODO

* check threaded view HS in Matrix blog PoC
* How to integrate well with Lemmy? Create a new thread/topic for each subthread?
  * Also simulate this if one changes the "subject" when replying in FluxBB?
