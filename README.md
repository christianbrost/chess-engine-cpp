# C++ Chess

2-player chess game, all rules included: move validation for every piece, castling, en passant, pawn promotion, check/checkmate/stalemate detection.

**[play in browser](https://christianbrost.github.io/chess-engine-cpp/)**

I wrote the game logic entirely myself in c++17, it initially only ran as a native SFML window. the separation of logic and SFML interface + the webassembly port for the browser I did with claude.

## structure

- `src/Board.h`, `src/Piece.h` – game logic, independent of SFML
- `src/main.cpp` – desktop version with SFML
- `src/wasm_bindings.cpp` – binds the same logic to javascript via embind
- `web/` – browser frontend (html/css/js)

## run

desktop (needs SFML 3):

```bash
cmake -B build && cmake --build build && ./build/chess_game
```

web (needs the emscripten sdk):

```bash
./build_wasm.sh
cd web && python3 -m http.server 8000
```
