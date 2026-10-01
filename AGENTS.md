# Repository Guidelines

## Project Structure & Module Organization

- `tetrish` is the executable Bash game. It contains board state, piece generation, collision detection, scoring, input handling, timing, and terminal rendering.
- `docs/` contains the static website: `index.html`, `style.css`, and `script.js`. Images and icons live in `docs/assets/`; `.nojekyll` supports GitHub Pages hosting.
- `README.md` documents installation, controls, platform requirements, and website publishing.
- There is currently no test suite, dependency manifest, or build pipeline. `tools/` is currently empty.

## Build, Test, and Development Commands

- `./tetrish`: launch the game in an interactive ANSI-compatible terminal. Requires Bash 4+ and `stty`; Bash 5+ is recommended for timing.
- `bash -n tetrish`: check Bash syntax without starting the game.
- `python3 -m http.server 8000 --directory docs`: serve the website at `http://localhost:8000`.
- `git diff --check`: check changes for whitespace errors before committing.

Neither the game nor the website requires a build step or package installation.

## Coding Style & Naming Conventions

Use two-space indentation in Bash and JavaScript. Follow existing Bash conventions: `snake_case` function names, uppercase shared state and constants, and lowercase `local` variables. Quote shell expansions where appropriate and preserve compatibility with Bash 4+. Keep terminal cleanup reliable when changing exit paths or signal handling.

JavaScript uses `const`, single-quoted strings, and semicolons. Match the existing HTML and compact CSS formatting; avoid unrelated reformatting. No formatter or linter is configured. Keep the game dependency-light and the website usable without a build tool.

## Testing Guidelines

No testing framework or coverage threshold is configured. Run the syntax and whitespace checks above. For gameplay changes, manually verify movement, rotation, both drop modes, line clearing, scoring, pause, restart after game over, and terminal restoration on exit. Check held drop keys across piece spawns when changing input handling.

For website changes, verify narrow and wide layouts, links, and copy-button behavior in a browser.

## Commit & Pull Request Guidelines

History uses concise imperative subjects, such as “Make game speed consistent across different CPUs.” Follow that style and keep commits focused.

In pull requests, describe the problem, resulting behavior, and checks performed. Link related issues when applicable. Include screenshots for website or terminal appearance changes, and update `README.md` when controls, requirements, or installation instructions change.
