# Crack The Vault – 4‑Digit Number Guessing Game

A simple, mobile‑friendly browser game where you try to crack a 4‑digit vault code in 4 tries. Digits 0–9 are all valid, digits may repeat, and the code is never 0000. Feedback uses the classic blue/yellow hints:

- Blue: Correct digit in the correct position
- Yellow: Correct digit, wrong position

## Quick start

- Just open `index.html` in your browser.
- Or serve locally (recommended for mobile testing):

```bash
# From the project folder
python3 -m http.server 8000
# Then open in your browser
xdg-open http://localhost:8000/index.html
```

## How to play

1. Enter a 4‑digit number (e.g., 0077) and press Guess.
2. Read the feedback:
   - Blue = digit and position match
   - Yellow = digit exists but in a different position
3. You have 4 total tries. If you crack the vault, you’ll see a clear “YOU WIN” banner. If you run out of tries, you’ll see “YOU LOSE” and the secret will be revealed.
4. Click “Play again” to start a new round.

## Features

- 4‑digit code, range 0001–9999 (0 allowed; 0000 excluded)
- Digits can repeat (e.g., 1001 is valid)
- Four attempts per game
- Per‑digit highlights on each guess (blue/yellow/gray)
- Guess history and clear win/lose banner
- Mobile‑friendly layout and inputs
- Accessible status updates via aria‑live regions

## Project structure

```
numbers-game/
├── index.html   # Game UI + logic (single file)
└── README.md    # This file
```

## Customization

All settings live in `index.html`.

- Tries per game: search for `triesLeft = 4` and change the value.
- Color/text theme: tweak the CSS variables at the top of the `<style>` block (e.g., `--blue`, `--yellow`, `--accent`).
- Prevent all‑zero code: implemented in `newSecret()` (keeps 0 valid but rejects 0000).
- Reveal the secret for debugging: uncomment the `console.log` line inside `reset()`.

## Notes and tips

- Input accepts exactly 4 digits; non‑digit characters are filtered out.
- Buttons are set to `type="button"` to avoid accidental submits; after game end the result banner takes focus so pressing Enter won’t auto‑reset.
- Works offline—no build step or dependencies required.

## Troubleshooting

- Nothing happens on Guess: ensure you entered exactly 4 digits (no spaces or letters).
- Keys don’t show a numeric keypad on mobile: most devices honor `inputmode="numeric"`, but behavior can vary by keyboard app.
- Styling looks off: try a modern browser (Chrome, Edge, Firefox, Safari).

---

© 2025 [Khagendra Poudel](https://github.com/khagendra-poudel)
