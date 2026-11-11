# Endgame

A single-file chess game you play against the computer, built with vanilla HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies.

## Features

- **Full chess rules:** castling, en passant, pawn promotion, check, checkmate, and stalemate
- **Computer opponent** with three difficulty levels (Easy, Medium, Hard)
- **Play as White or Black**
- **Move hints:** click a piece to see its legal moves, with dots for moves and rings for captures
- **Undo** your last move (and the computer's reply)
- **Captured pieces** tray with a running material count
- **Move log** in standard algebraic notation (e.g. `Nf3`, `exd5`, `O-O`, `Qh5+`)
- Highlights for the last move and for a king in check
- Responsive layout that works on desktop and mobile

## Getting started

No installation needed. Download or clone the repo and open `chess.html` in any modern browser:

```bash
git clone <your-repo-url>
cd <your-repo-folder>
open chess.html        # macOS
# or double-click the file in your file explorer
```

### Hosting on GitHub Pages

1. Rename `chess.html` to `index.html`
2. In your repo, go to **Settings → Pages**
3. Set the source to your main branch and save

Your game will be live at `https://<username>.github.io/<repo-name>/`.

## How to play

1. Click one of your pieces to select it
2. Click a highlighted square to move there
3. The computer replies automatically

Use the side panel to change difficulty, switch sides, undo, or start a new game. Changing sides starts a new game.

## How the AI works

The opponent uses **minimax search with alpha-beta pruning**. Positions are scored by material value plus piece-square tables, which reward good placement such as central knights, advanced pawns, and a castled king.

| Level  | Search depth |
|--------|--------------|
| Easy   | 1 ply        |
| Medium | 2 ply        |
| Hard   | 3 ply        |

When several moves score equally, the computer picks one at random, so games don't repeat.

## Project structure

Everything lives in one file:

```
chess.html
├── <style>    Board, pieces, and side panel styling
└── <script>   Move generation, rules, AI, rendering, and controls
```

## Known limitations

- Pawns always promote to a queen
- No threefold repetition or fifty-move rule draws
- The AI is a shallow search, so strong players will beat it, especially on Easy and Medium
- Fonts (Fraunces, Inter, JetBrains Mono) load from Google Fonts, so offline play falls back to system fonts

## Ideas for improvements

- Choose the promotion piece
- Move ordering and quiescence search for a stronger AI
- Drag-and-drop moves
- Save and load games (PGN export)
- Sound effects and move animations

## License

Add a license of your choice (MIT is a common default for small projects).
