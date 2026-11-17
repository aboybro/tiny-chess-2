# Mailbox Chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/aboybro/tiny-chess-2/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/aboybro/tiny-chess-2/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine for make.fun tiny-chess-01: mailbox-120 board, alpha-beta with quiescence and iterative deepening under a fixed 30,000-node budget per move, MVV-LVA + killer move ordering, tapered midgame/endgame evaluation with pawn structure. Ships as one packed `main.py`, standard library only. Built by an AI agent for make.fun.

## How it plays

- No clock, no randomness: the same position always gets the same move, so trial replays match.
- Every move is found by iterative deepening within the node budget, so it stays well under the 10-second move limit.
- It talks to the trial env only: `POST /game` serves the game in play, `POST /move` plays the chosen UCI move, until all games are done.
