# Adversarial State-Space Optimization in Chess Environments

Project documents for **CS23533 – Foundations of Artificial Intelligence** (III Year / V Semester, 2026–2027 Odd Semester), Department of Computer Science and Engineering (Cyber Security), Rajalakshmi Engineering College, Chennai.

This repository holds the project report and the review presentations. The engine's source code lives in a separate repository (see [Links](#links)).

## About the project

A classical AI chess engine built from first principles, with no machine learning, neural networks or external chess libraries. Chess is modelled as a fully observable, deterministic, zero-sum state space and played by a goal-based agent.

- **Move generation**: a self-built 64-square board representation with FEN support. It matches the published perft node counts on all seven standard test positions.
- **Evaluation**: a hand-crafted function combining material, piece-square tables, pawn structure, king safety and mobility.
- **Search**: Negamax with Alpha-Beta pruning, Iterative Deepening within a time budget, Quiescence Search, MVV-LVA move ordering, null-move pruning, configurable contempt and a fixed-size Zobrist-hashed transposition table.
- **Interface**: the engine runs in a Web Worker behind a React UI with time controls, typed moves (SAN/UCI) and a teaching mode that compares Minimax, Alpha-Beta and other search configurations side by side.
- **Delivery**: deployed to Firebase Hosting through a GitHub Actions pipeline gated by 53 automated tests.
- **Security**: STRIDE threat model of the deployed application, with proposed controls for its build pipeline and hosting.

### Key results

| Result | Value |
| --- | --- |
| Node reduction vs. plain Minimax (depth 4, ordering + TT) | ~110× |
| Agreement with plain Minimax (Alpha-Beta, ordering, TT) | 79 / 79 searches, same move and score |
| Start position, depth 5 | 5,072,213 nodes (Minimax) → 58,390 nodes (Alpha-Beta + MVV-LVA + TT) |
| Null-move pruning, self-play | about +130 Elo |
| Playing strength vs. Stockfish 19 (calibrated `UCI_Elo`, 1 s/move) | roughly 1600–1700 |

## Repository contents

| File | Description |
| --- | --- |
| [`FOAI - Project Report (16, 57).docx`](<FOAI - Project Report (16, 57).docx>) | Full project report covering design, threat model, experiments and results |
| [`FOAI - 0th Review (16, 57).pptx`](<FOAI - 0th Review (16, 57).pptx>) | Zeroth review presentation (31.07.2026) |
| [`FOAI - 1st Review (16, 57).pptx`](<FOAI - 1st Review (16, 57).pptx>) | First review presentation (25.09.2026) |
| [`FOAI - 2nd Review (16, 57).pptx`](<FOAI - 2nd Review (16, 57).pptx>) | Second review presentation |
| [`FOAI - Model Review (16, 57).pptx`](<FOAI - Model Review (16, 57).pptx>) | Model review presentation |

## Links

- Source code: https://github.com/SaIdEeVaN/FOAI-Project
- Live prototype: https://foai-chess-engine.web.app

## Team

- Baviri Setty Sai Deevan (2116241901016)
- Monish Priyan M (2116241901057)

**Supervisor:** Dr. Bhuvana S, Ph.D., Assistant Professor (SG), Department of Computer Science and Engineering (Cyber Security)
