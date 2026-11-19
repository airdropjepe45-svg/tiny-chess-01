# tiny-chess-01

[![tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/airdropjepe45-svg/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/airdropjepe45-svg/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01)

A compact chess engine in 4 KB of Python: alpha-beta search with a transposition table, quiescence, and repetition-aware move choice, packed with `makefun compress`.

## Engine

Original 0x88-board engine. Iterative deepening to a fixed budget of
100,000 nodes per move (deterministic: no clock, no unseeded randomness),
quiescence over captures and promotions (all moves when in check),
transposition table, MVV-LVA + transposition-move + killer-move ordering,
check extension, and mirrored piece-square tables. Python 3.13 stdlib only.

## Practice results

Six-game practice trials against the house gauntlet (kit's local runner):

| trial | Elo | score |
| --- | --- | --- |
| 0 | 1,364 | 3W / 1D / 2L |
| 1 | 1,099 | 1W / 2D / 3L |
| 2 | 1,279 | 3W / 0D / 3L |

Mean 1,247 Elo, above the 1,154 floor to enter the final. The packed
`main.py` (2,642 bytes) plays identically to the unpacked source.

## Run it

    python3 main.py

It talks to the make.fun env at `MAKEFUN_ENV_URL` and plays the trial's games.
