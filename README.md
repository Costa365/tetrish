# TetriSH

Pure Bash Tetris for Linux terminals with minimal dependencies.

## Run

```bash
./tetrish
```

Use an ANSI-compatible terminal with Bash 4+ and `stty`. Bash 5+ is
recommended for smooth timing. The game uses associative arrays, so macOS's
bundled Bash is too old.

## Download directly from GitHub

No separate download server or build step is needed:

```bash
curl -fL https://raw.githubusercontent.com/Costa365/tetrish/main/tetrish -o tetrish
chmod +x tetrish
./tetrish
```

On macOS, install [Homebrew](https://brew.sh/), then use its Bash explicitly:

```bash
brew install bash
curl -fL https://raw.githubusercontent.com/Costa365/tetrish/main/tetrish -o tetrish
"$(brew --prefix)/bin/bash" ./tetrish
```

The macOS instructions have not yet been tested on a Mac. Linux instructions
may also work inside Windows WSL; native Windows terminals are not supported,
and WSL has not yet been tested.

## Controls

- Left/Right arrows: move
- Down arrow: soft drop
- Up arrow: hard drop
- `x`: rotate clockwise
- `z`: rotate counter-clockwise
- `p`: pause / unpause
- `s`: start a new game (after game over)
- `q`: quit

## Notes

- Uses ANSI terminal escapes and `stty`.
- Shows the next piece.
- Shows game play keys.
- Uses a 10x20 board and classic single/dual/triple/tetris scoring.
- Shows a landing ghost and increases speed every ten cleared lines.

## Website

The static website lives in `docs/`. There are no dependencies or build steps.
Preview it locally:

```bash
python3 -m http.server 8000 --directory docs
```

Open http://localhost:8000 in your browser.

To publish using [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site):

1. Commit and push the website files to `main`.
2. Open the repository's **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose **main** and **/docs**, then save.

The expected URL is https://costa365.github.io/tetrish/ once Pages is enabled
and its deployment finishes. A public repository can use GitHub Pages on
GitHub Free. The website can also be hosted by any static web server by copying
the contents of `docs/`.

The game screenshot is stored in `docs/assets/tetrish.png` and displayed inside
a terminal-style frame. Replace that image to update the screenshot.
