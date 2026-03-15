# TertriSH

Pure Bash Tetris for Linux terminals with minimal dependencies.

## Run

```bash
./tetrish
```

## Controls

- Left/Right arrows: move
- Down arrow: soft drop
- Up arrow: hard drop
- `x`: rotate clockwise
- `y`: rotate counter-clockwise
- `p`: pause / unpause
- `q`: quit

## Notes

- Uses ANSI terminal escapes and `stty`.
- Shows the next piece.
- Uses a 10x20 board and classic single/dual/triple/tetris scoring.
