# Backend optional portal search

## Problem statement

* Given a knowledge repository for user generated content, for example a wiki or a forum.
* Up to a few items will be changed (wiki) or inserted (forum) every day.
* Multiple days of indexing latency is acceptable.
* The task is to provide full text search through static web hosting.
* [backend-optional-web-apps.md](backend-optional-web-apps.md)

## Architectural considerations

* Whether it is acceptable to show stale content
* What is the total size of the database
* How many items does our database contain
* How often the database needs to be updated
* The amount of incremental difference between database updates
* Server storage quota
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
* It may reduce server storage due to block size overheads

## Algorithms

### Database indexing tiers

If a document to be indexed can be decomposed into parts that differ in orders of magnitude, they can be indexed separately.
For example, a document may have a title, keywords, picture alt texts and summary along with its textual body.

In certain cases, it could be feasible to handle the smaller subsets with full replication that can also offer a live preview in search results.

### Normalization

* Stop words should be removed.
* Case folding
* Stemming
* Try to find word compositions and add their individual constituents with a lower weight to the index

### n-grams

* If only 1-grams are handled, in case of certain word phrases, add them both together and its individual constituents to the index (e.g, hyphen, underscore, email, matrix ID, hostname, phone number, camelcase)
* It would be desirable to at least index 2-grams.
* Detect whether certain phrases are prone to misspelling with regards to one word, two words and hyphenated form. Weekly connect them during indexing or lookup if yes.
* Insert word pairs within up to 5 words of distance as near-pairs
* OpenStreetMap key-value tags

### Alternatives

Depending on the replication strategy, synonyms and typos should be either:

* added to the index or
* looked up

### Search

* Quoted phrase: decompose to n-grams
* AND, OR, NOT: operations on result sets of individual word queries
* NEAR (based on near-pair 2-grams)
* date field
* author field
* offer to index and search both individual documents (comments) and when combined as chains (threads)

### Ranking

* filter or rank based on whether it is present in the title, keywords, picture alt texts or summary
* rank based on relative incidence count
* https://en.wikipedia.org/wiki/Tf%E2%80%93idf
* https://en.wikipedia.org/wiki/Okapi_BM25

### Persistent document storage

* No input content to avoid copyright infringement
* May be admissible: URL's, dates, times, numeric values and OSM tags occurring within content
* SHA256 sum
* Original URL
* How many times does each word and n-gram occur within the document
* Message-ID
* Subject (pointer to separate table)

### Ephemeral global storage

* Total number of documents

### Ephemeral document storage

* Total word count within each document
* How many times does the word with the highest incidence occur within each document
* For each document, which word within a given document occurs in the most documents and how often?
* Which phrases within the document have been cited in other documents? Their weight weight should be increased at the origin and decreased at points of citation.

### Ephemeral word storage

* Count of documents that contain a word
* optional: Number of times a word occurs globally
* Computed global correction factor of a word (idf)
* Which documents contain a word, how many times and with what adjusted frequency (optional: at which positions if copyright permits)
