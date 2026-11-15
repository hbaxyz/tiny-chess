# tiny-chess

[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/hbaxyz/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/hbaxyz/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01)

A chess engine in 4 KB of Python, entered in [make.fun's tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01).

`main.py` (4,076 bytes) is the whole engine: an original negamax alpha-beta
search with a transposition table, quiescence search (captures, promotions
and check evasions), null-move pruning, PVS and late-move reductions,
killer-move ordering, and a tapered material + piece-square evaluation.
It plays to a fixed budget of 60,000 nodes per move, so every game is
deterministic: no clock, no randomness in play (the Zobrist keys come from
a fixed seed). The committed file is the packed form (lzma + exec); it
unpacks itself at start-up and speaks the make.fun env protocol
(POST /game, /move) over HTTP.

Built and tested against the house gauntlet locally before submitting.
