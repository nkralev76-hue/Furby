# Furby Chess Engine

UCI chess engine by **nkralev76-hue** — C++17, Syzygy tablebases, Lazy SMP.

Furby is a 0x88 + bitboard hybrid engine focused on time-control play. Latest stable is **1.49**.

## What's inside

- **Search:** alpha-beta + PVS, null-move, LMR, quiescence, check & singular extensions (PV depth>=8), TT (64 MB), killers/history/counter-move history, pawn correction history
- **Eval:** tapered PST, bishop pair, pawn structure, king safety (weak squares + ring mobility), mobility, outposts, rook on 7th/6th
- **Other:** Syzygy WDL/DTZ (Fathom), MultiPV 1..10, portable Windows build

## Download

See **Releases** → `Furby_1.49_portable.exe` (portable, `-march=x86-64 -static`, no DLLs).

Perft(5) startpos: `4865609`.

## Usage

```text
uci
isready
position startpos
go depth 12
setoption name MultiPV value 3
setoption name Hash value 256
```

Or in Arena / CuteChess / Banksia: add as UCI engine, set Hash/Threads.

## Versions

- **1.49** — 1.48 + singular extensions (PV) + MultiPV fix. Portable build.
- **1.48** — SearchParams SPSA infrastructure (15 tunable search params, defaults = 1.47).
- **1.47** — speed pass (att/bitboard, SEE memo, lazy givesCheck) +9.6% NPS.
- Earlier: see `Versions/versions.txt` in private dev history.

## License

Proprietary — see `LICENSE`. Binary free to use; source not licensed.
