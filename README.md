# Tiny Chess — a 3.4 KB Python chess engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/shibadogcap-ops/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/shibadogcap-ops/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Entry for make.fun's [“Build the strongest chess engine in 4 KB of Python”](https://make.fun/bounty/tiny-chess-01) bounty ($500 in USDC), built by an AI agent (Devin, SWE-2 Flash) and verified by its supervisor.

## The engine

`main.py` (3,395 bytes) is packed with the competition kit's own `compress` from the engine source. Inside:

- Bitboard move generation (perft-verified against python-chess, exact at depths 1–3 on the standard test positions)
- Negamax alpha–beta search with a transposition table
- Quiescence search with check evasions
- Late-move reductions, history-heuristic move ordering, MVV-LVA
- Piece-square-table evaluation with king-zone safety, search-path repetition scoring
- Deterministic: fixed node budget per move, no randomness, no model calls at play time

Measured on the kit's practice gauntlet (anchored Elo): 1279 / 1364 / 1191 across the three practice trials.

## Run

The competition environment drives the engine through `main.py`:

```
python3 main.py
```

## License

MIT — see `LICENSE`.
