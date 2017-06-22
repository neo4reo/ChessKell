

## Chess engine written in Haskell.

There are 3 supported game modes:
- human vs human with computer evaluation for the best move (terminal-only)
- engine vs engine where the output of the game is piped to GNU xboard (GUI)
- human vs engine (GUI with xboard)

Originally minimax algorithm was used for picking moves, but now engine also supports Alpha-Beta pruning.

Chesskell is a fun side-project and is not meant to compete with other modern chess engines, therefore it has not been optimized for performance.

Performance is decent with the default scan depth of 4, but starts getting slow when using 5-move scan-depth.

#### Installation

`cabal install matrix either`

#### Running

`make gui`  - player vs bot xboard GUI

`make run`  - player vs player terminal-only

`make gui2` - bot vs bot xboard GUI

### TODO
- [x] multi-threading
- [x] castling (works correctly)
- [ ] en-passant
   - [ ] add last move to the Board structure
- [ ] pawn promotion
   - [x] always promotes to queen
   - [ ] promoting to other pieces is not yet implemented
- [ ] heuristics for better picking moves
- [ ] opening book
- [ ] change Board structure to include list of possible moves so the work isn't duplicated and adding heuristics is simpler
- [ ] parse command line arguments so the engine doesn't need to be recompiled when switching game modes

