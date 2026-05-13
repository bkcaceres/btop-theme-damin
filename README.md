# btop-theme-damin

> A btop theme matching the rest of the damin set. Two-color palette `#98ABCC` (blue) → `#E890B0` (pink) on `#1e1e1e`. Cool to warm reads as calm to active — outlines stay blue, titles and selections go pink, graphs gradient through a mauve midpoint.

```
       ╭── cpu ─────────────────────╮   ╭── mem ─────────────────────╮
       │   ▁▂▃▄▅▆▇█▇▆▅▄▃▂▁          │   │  used   ████████░░  62 %   │
       │   blue → mauve → pink      │   │  free   ██████████   38 %  │
       ╰────────────────────────────╯   ╰────────────────────────────╯
```

Designed to feel like a continuation of [`fish-theme-damin`](https://github.com/miniex/fish-theme-damin) and [`dotfiles.tmux`](https://github.com/miniex/dotfiles.tmux) / [`dotfiles.kitty`](https://github.com/miniex/dotfiles.kitty) — same palette, same `#1e1e1e` ground, same restraint.

## Palette

| Role                       | Color     |
|----------------------------|-----------|
| Background                 | `#1e1e1e` |
| Foreground                 | `#ffffff` |
| Blue (outlines, low / cool)| `#98ABCC` |
| Pink (titles, high / warm) | `#E890B0` |
| Mauve (gradient midpoint)  | `#C09EBE` |
| Meter trough               | `#2a2a2a` |
| Divider                    | `#3a3a3a` |
| Inactive text              | `#555555` |

Reds for danger and greens for safety are intentionally absent — heat / load is signalled by saturation drifting from blue toward pink, not by a third hue.

## Install

**One-liner (curl):**

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/miniex/btop-theme-damin/main/install.sh)"
```

The installer copies `damin.theme` into `~/.config/btop/themes/` and, if you confirm, rewrites the `color_theme` line in `~/.config/btop/btop.conf` to point at it.

**Manual:**

1. Copy the theme file:
   ```bash
   mkdir -p ~/.config/btop/themes
   curl -fsSL https://raw.githubusercontent.com/miniex/btop-theme-damin/main/damin.theme \
     -o ~/.config/btop/themes/damin.theme
   ```
2. Open btop, press <kbd>Esc</kbd> → **Options** → **color_theme** and pick `damin`.

   Or edit `~/.config/btop/btop.conf` directly:
   ```
   color_theme = "damin"
   ```

## Notes on the gradients

- `temp_*`, `cpu_*`, `download_*`, `upload_*`, `process_*` all run **blue → mauve → pink**. Higher value = warmer color.
- `used_*` lives entirely in the **pink family** (`#A3677D` → `#F5B2C8`) — distinct from cpu/temp so a glance at the meters separates "occupied" from "loaded."
- `free_*`, `cached_*`, `available_*` stay in the **blue family** — abundance reads as calm.
- Box outlines (`cpu_box`, `mem_box`, `net_box`, `proc_box`) are blue; titles are pink. Same convention as the tmux pane borders.

## Companion repos

- [fish-theme-damin](https://github.com/miniex/fish-theme-damin) — fish prompt
- [dotfiles.tmux](https://github.com/miniex/dotfiles.tmux) — tmux config
- [dotfiles.kitty](https://github.com/miniex/dotfiles.kitty) — kitty terminal config
- [dotfiles.nvim](https://github.com/miniex/dotfiles.nvim) — Neovim config

## License

[MIT](LICENSE) © 2026 Han Damin
