# tiny-chess-01

A chess engine in 4,096 bytes of Python (stdlib only, Python 3.13),
written for the make.fun tiny-chess-01 bounty.

Engine: 0x88 board, negamax with alpha-beta, quiescence search (captures
and check evasions), transposition table with Zobrist hashing, killer-move
ordering, MVV-LVA capture ordering, null-move pruning, check extensions,
late-move reductions, iterative deepening under a fixed 45,000-node budget
per move, and piece-square-table evaluation. Fully deterministic: the same
position always gets the same move, so replays are byte-identical.

`main.py` is the whole engine: an lzma-compressed payload with a tiny
unpacker. Run it with `MAKEFUN_ENV_URL` set; it plays the gauntlet through
the env (`POST /game`, `POST /move`) until every game is over.

License: MIT.
