# tiny-chess-01 entry

A chess engine in 4 KB of Python (MIT, see LICENSE).

- `main.py` is the whole engine, packed with the kit's `makefun compress`
  (LZMA payload + stub); the readable source is `source.py` in this folder
  (not committed — `bundle` uploads it beside the sessions, and the
  transcript check counts its lines in `main.py`'s place).
- 0x88 board, alpha-beta with transposition table, killer moves, null-move
  pruning (R=2) and late-move reduction, capture quiescence with check
  evasions and delta pruning, material + piece-square + bishop-pair eval
  (queenless-endgame king centralisation).
- Fixed node budget per move (100,000 nodes, iterative deepening to depth 6),
  never a clock, no randomness: replays play the same moves.
- Talks to the env alone (`POST /game`, `/move`, `/resign`).

Local practice trial (kit env server, trial-0): see `../NOTES.md`.
