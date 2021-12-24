# Delay tolerant multiplayer network games

## Scope

* Games that can scale globally due to not requiring an expensive centralized game server for state synchronization (and game logic).

## Implementation

* Such a game could be ran mostly client side and offline.
* It could implement some established federated communication protocol for state synchronization (like XMPP, matrix, ActivityPub, email, etc.).
  * It could piggyback onto a federated social networking service instead of implementing such a server from scratch.
* It could piggyback minimal backend logic onto an addon of a commonly deployed application server:
  * [../../hu/service/game-backend.md](../../hu/service/game-backend.md)

## Game style

### Simultaneous play

* Offset the greater delay between steps that reduces gratification
* Encourage player to play multiple, visually vastly different games at the same time
* In a given round, all players might be required to make their move simultaneously
  * Epoch based turns
    * Enforce time limit agreed by all before the game (5min, 1h, 24h)
    * In case of timeout, the player either loses or a default move gets substituted
  * Alter rules to allow merging the resulting state in a deterministic manner
  * The play could be held on multiple dimensions (i.e., have a separate lane for each player but synchronize actions based on property and cash amount)
  * Apply changes only for the next turn
  * Alter rules to resolve conflicts randomly

### Player attraction

* New players should be introduced to the game
* Former players should be reminded what they have achieved thus fur, with whom have they played and whether any of them have logged in since leaving

### Player count

* Allow a large number of players to participate in the same game (being able to interact)
  * Make single player games (`sgt-puzzles`) competitive
    * Scoring, time
    * Highlighting whether a sequence (3-gram?) of good (or bad) moves have been executed by a friend
    * Announcing after each achievement how many of your friends have reached this level and what percent of your friends have you beaten
    * Betting on a match between two friends based on following their play
    * Estimating the completion percentage of the puzzle based on elapsed time or moves
  * Make single player games cooperative
    * Allow multiple cursors to solve multiple parts of a puzzle at the same time
    * Chat between participants to discuss constraints or ask questions
    * To balance action rate of the two players, track historical performance and assign the more difficult parts to the faster player
* Games should last long (or indefinitely)
  * Allow late joiners
  * Early leavers should have a partial reward (score)
  * Players should be incentivized to not leave early (periodic rewards superlinear to in-match time)

## Games for inspiration

### Single player

* `sgt-puzzles`
* mahjongg

### 2-player

* chess
* backgammon
* checkers

### More than 3 players

* https://en.wikipedia.org/wiki/Consequences_(game)
* https://en.wikipedia.org/wiki/Exquisite_corpse
* https://en.wikipedia.org/wiki/Mad_Libs
* https://en.wikipedia.org/wiki/Apples_to_Apples
* https://en.wikipedia.org/wiki/Cards_Against_Humanity
* https://en.wikipedia.org/wiki/Telephone_Pictionary#Variants
  * https://en.wikipedia.org/wiki/Rebus
  * https://en.wikipedia.org/wiki/Broken_Picture_Telephone
  * https://en.wikipedia.org/wiki/Drawception
* https://en.wikipedia.org/wiki/Draw_Something
  * https://en.wikipedia.org/wiki/Pictionary_(video_game)

### TODO

* tavlou
* Chain Reaction (up to 4 players to be sane but more possible)
* strategy card games
  * something similar to pokemon
  * something similar to "magic the gathering"
  * YuGiOh-like
