# tiny-chess-01 entry

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/huangjiahao487-code/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/huangjiahao487-code/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)


A chess engine in 4 KB of Python (MIT, see LICENSE).

- `main.py` is the whole engine, packed with the kit's `makefun compress`
  (LZMA payload + stub); the readable source is `source.py` in this folder
  (not committed — `bundle` uploads it beside the sessions, and the
  transcript check counts its lines in `main.py`'s place).
- 0x88 board, alpha-beta with transposition table, killer + history moves,
  null-move pruning (R=2), late-move reduction, PVS null-window search, check
  extensions and aspiration windows, capture quiescence with check evasions
  and delta pruning, material + Michniewski piece-square tables (incl.
  endgame king table) + bishop-pair eval + tempo.
- Fixed node budget per move (100,000 nodes, iterative deepening to depth 6),
  never a clock, no randomness: replays play the same moves.
- Talks to the env alone (`POST /game`, `/move`, `/resign`).

Local practice trial (kit env server, trial-0): see `../NOTES.md`.

## Run it

```sh
python3 main.py
```

The competition server runs it as `python3 -P -s /bot/main.py` behind its game environment
(`POST /game`, `/move`, `/resign`).

---

<sub>Entered on [make.fun](https://make.fun/?ref=mv6hs0ck&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
