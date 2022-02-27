# Backend-optional portal search

## Problem statement

* Given a knowledge repository for user generated content
* Up to a few items will be changed (wiki) or inserted (forum) every day.
* Multiple days of indexing latency is acceptable.
* The task is to provide full text search through static web hosting.
* [backend-optional-web-apps.md](backend-optional-web-apps.md)

### Use cases

* wiki article or section: history size, editor count and watcher count as article popularity, view count if available
* forum, mailing list: include reply count as popularity of thread, view count if available
* source code or documentation within a VCS code hosting repository: include changeset comments and co-occurrence as weak links, count of changesets, committers, commit days or merges as file popularity, fewer TODO/FIXME, consider indexing all versions of documents
* FOSS cross-project translation memory
* text within OpenStreetMap: consider nearby or overlapping entities, fuzzy handling of house number, street and locality

## Architectural considerations

### Deciding factors

* Whether it is acceptable to show stale content
* What is the total size of the database
* How many items does our database contain
* How often the database needs to be updated
* The amount of incremental difference between database updates
* Server storage quota: size and inode count (files and directories)
* Server monthly network transfer quota both for updating and visits
* The number of actions and repeat visits a single user will make
* The initial and repeated action latency that a user can tolerate
* The total transferred data over the network that a user can tolerate if it is metered
* The link speed of the user with the lowest bandwidth that we should target

### Full replication

Cache the whole database at the client if

* The total size of the database is much smaller than what a user can tolerate as a full download
* The client can tolerate stale data
* Can be update incrementally and in a lazy fashion, ideally only when a query proves that it might be stale or on demand.

### One record per file

Request a separate file for each keyword and use further indirection for deduplication if

* Client bandwidth is metered
* Server storage is ample
* Server can handle a little higher load by receiving a higher number of smaller requests
* There is little or no correlation between neighboring records.
* The client is sensitive to stale data
* The database is large, changes frequently or is difficult to update incrementally

### Lazy replication

* Bundle records together based on correlation, predicting future requests or by preseeding globally popular records
* Ideally cryptographically sign the bundles on the server side so clients can replicate them between other clients over WebRTC
* It may reduce server storage due to block size overheads and inode count

## Crawler

* Incremental reindexing
* Continuation
* Ideally provide a feed of changed items (or even the diff)
* Ignore unchanged items based on hash

## Algorithms

### Database indexing tiers

If a document to be indexed can be decomposed into parts that differ in orders of magnitude, they can be indexed separately.
For example, a document may have a title, keywords, picture alt texts and summary along with its textual body.

In certain cases, it could be feasible to handle the smaller subsets with full replication that can also offer a 0RTT live autocomplete and live preview in search results

### Normalization

* Stop words should be removed.
* Case folding
* Accent folding
* Try to find word compositions and add their individual constituents with a lower weight to the index
* Stemming: store the root in place of or in addition to the word (with lower weight)
* https://tartarus.org/martin/PorterStemmer/
* https://snowballstem.org/algorithms/
* https://en.wikipedia.org/wiki/Lemmatisation

### n-grams

* If only 1-grams are handled, in case of certain word phrases, add them both together and its individual constituents to the index (e.g, hyphen, underscore, email, matrix ID, hostname, phone number, camelcase)
* It would be desirable to at least index 2-grams.
* Detect whether certain phrases are prone to misspelling with regards to one word, two words and hyphenated form. Weekly connect them during indexing or lookup if yes.
* Insert word pairs within up to 5 words of distance as near-pairs
* Insert word pairs within the same document as co-occurring pairs if the result set of a single word would be too large
* Deduplicate index: remove a higher level n-gram if the results and ranking would be the same without it (i.e., they co-occur within the same sets of documents)
* OpenStreetMap key-value tags

### Alternatives

Depending on the replication strategy, synonyms and typos should be either:

* added to the index or
* looked up

### Hyperlinking

* If the content to be indexed supports hyperlinks
* Linked documents in HTML wiki, markdown, gemini
* Labeling embedded media files
* In case of forum threads, detect hyperlinks based on direct replies, citation, repeated keywords in text and user name
* Propagate ranking based on popularity
* https://en.wikipedia.org/wiki/Pagerank#Simplified_algorithm
* Weigh often cited parts as being more important
* Inherit some of the keywords from the text surrounding each link origin

### Search

* Quoted phrase: decompose to n-grams
* AND, OR, NOT: operations on result sets of individual word queries
* NEAR (based on near-pair 2-grams)
* date field
* author field
* offer to index and search both individual documents (comments) and when combined as chains (threads)
* attachment
* similarity to item: if the search box is on each page or based on user query or interaction
* limited wildcard search: prefixes only if path index replicated, infixes and suffixes only if the confusion set is small (<10 words)
* word stemming

### Single word autocomplete

* based on the item suffix tree
* edit distance based spelling suggestion for typos based on path index

### Multi-word autocomplete

* intersect single word suggestion with result set for previous words

### Ranking

* filter or rank based on whether it is present in the title, keywords, picture alt texts or summary
* rank based on relative word incidence count, PageRank, date of creation and last update, searches (if server log available)
* https://en.wikipedia.org/wiki/Tf%E2%80%93idf
* https://en.wikipedia.org/wiki/Okapi_BM25
* https://mediawiki.org/wiki/Search/Old#Search_Weighting_Ideas

## Storage

### Persistent document metadata

* Original URL
* May encode the post date on some platforms
* SHA256 sum of original input: to ensure integrity before showing user
* Should not contain free form textual content from input to avoid copyright infringement
* May be admissible: URL's, dates, times, numeric values and OSM tags occurring within content
* Attachment name, kind, size: for preview and filtering
* Thread references, In-Reply-To and implicit links based on which other item it cites: for PageRank and result tree visualization
* Message-ID: to facilitate reply
* Subject text: pointer to separate table, for preview or regexp search
* If possible, the whole set could be fully replicated on the client
* Available analytics related to popularity: count of views, reactions, watchers, edits, editors, days of edits

### Persistent document mirror

* If the input text is copyleft
* The whole original file for navigating and for previewing if the document is short (<4kB compressed)
* Slices of overlapping ranges of the input if the document is a long form webpage or source code (i.e., items usually >>4kB)
* Each slice may contain the matadata for the whole document to spare a separate query in case it is not replicated fully on the client

### Persistent document index

* How many times does each word and n-gram occur within the document: for index

### Ephemeral global index

* Total number of documents

### Ephemeral document index

* How many links point towards the document
* Which other documents are similar
* https://en.wikipedia.org/wiki/SimRank
* Total word count within each document
* How many times does the word with the highest incidence occur within each document
* For each document, which word within a given document occurs in the most documents and how often?
* Which phrases within the document have been cited in other documents? Their weight should be increased at the origin and decreased at points of citation.

### Ephemeral document path index

* For autocomplete
* Also enables bundling indexes of multiple documents together without having to do a binary search for endpoint existence checking
* May include the rank of each path (maximum in case of bundles)
* With partial replication, only list intermediate non-leaf paths that provide path dereferencing to access lower levels

### Ephemeral word index

* Count of documents that contain a word
* optional: Number of times a word occurs globally
* Computed global correction factor of a word (idf)
* Which documents contain a word, how many times and with what adjusted frequency (optional: at which positions if copyright permits)

## References

* https://sphider.worldspaceflight.com/about.php
