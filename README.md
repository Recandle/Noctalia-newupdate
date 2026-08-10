# Noctalia-newupdate

A later, tidier take on my [niri](https://github.com/YaLTeR/niri) + [noctalia-shell](https://docs.noctalia.dev) setup. Where [Noctalia-backup](https://github.com/Recandle/Noctalia-backup) was a flat dump of whatever needed saving, this one splits the niri config into separate files pulled in with `include`.

## Contents

### niri

| File | What it sets |
| --- | --- |
| `display.kdl` | Outputs. `DP-1` at 2560x1440@99.946 as the primary at `0,0` with `focus-at-startup`, `HDMI-A-2` at 1920x1080@60 to its right, and the laptop panel `eDP-1` switched off. |
| `layout.kdl` | 16px gaps, single columns always centered, focus ring and border both off, transparent background, and preset column widths at ⅓ / ½ / ⅔. |
| `rules.kdl` | Window rules and blur — 3 passes, offset 3.5, noise 0.02, saturation 1.7, 20px corner radius, and 0.74 opacity. The comments record what neighbouring opacity values look like, since that one number decides how much wallpaper reads through. |
| `misc.kdl` | Top-level odds and ends: `prefer-no-csd`, Wayland and Qt environment variables, the `capitaine-cursors` theme at size 24, hotkey overlay skipped at startup, and `honor-xdg-activation-with-invalid-serial` so noctalia's notification actions and window activation work. |
| `autostart.kdl` | Starts `qs -c noctalia-shell` and `blueman-applet`. |
| `keybinds.kdl` | Key bindings, with noctalia driven over IPC (`qs -c noctalia-shell ipc call ...`). |

### Everything else

| File | Goes to | What it is |
| --- | --- | --- |
| `settings.json` | `~/.config/noctalia/` | noctalia-shell settings dump. |
| `configfastfetch.jsonc` | `~/.config/fastfetch/` | fastfetch config. |
| `kittybackup.conf` | `~/.config/kitty/` | Just the transparency lines — 0.25 background opacity with blur at 120. The comment is a reminder that the `background` colour has to stay commented out or the blur is painted over. |

## Requirements

niri, Quickshell, noctalia-shell, kitty, fastfetch, blueman, and the `capitaine-cursors` theme.

## Before you use it

The output names and modes in `display.kdl` are specific to this machine — set your own before using it, or you will end up with a blank or misplaced desktop. `settings.json` and `configfastfetch.jsonc` also reference paths under `/home/sannur`.

## Caveats

Single commit from May 2026, kept as a restore point rather than a maintained config. The inline comments are in Indonesian.

## License

GPL-3.0. The niri files here started as copies of the config CachyOS ships in
[cachyos-niri-noctalia](https://github.com/CachyOS/cachyos-niri-noctalia), which is
GPL-3.0, so this repo inherits it. [NOTICE](NOTICE) lists what came from where.
