<div align="center">
  <img src="dpcode-icon.png" alt="DP Code icon" width="128" />

# dpcode AUR packages

[![AUR version](https://img.shields.io/aur/version/dpcode-bin?style=flat-square&label=AUR)](https://aur.archlinux.org/packages/dpcode-bin)
[![AUR votes](https://img.shields.io/aur/votes/dpcode-bin?style=flat-square&label=votes)](https://aur.archlinux.org/packages/dpcode-bin)
[![AUR last updated](https://img.shields.io/aur/last-modified/dpcode-bin?style=flat-square&label=updated)](https://aur.archlinux.org/packages/dpcode-bin)
[![License](https://img.shields.io/badge/license-MIT-111111?style=flat-square)](./LICENSE)

Automated AUR packaging for **DP Code** on Arch Linux.

</div>

## Install from the AUR

Use your favorite AUR helper:

```bash
yay -S dpcode-bin
# or
paru -S dpcode-bin
```

## What this repo does

- Tracks upstream DP Code releases.
- Packages the upstream x86_64 AppImage for Arch Linux.
- Publishes `dpcode-bin` to the AUR automatically.

## T3 Code State

This package skips DP Code's automatic T3 Code state import by default. DP
Code has diverged from T3 Code, and T3 Code state can contain schema shapes
that crash the DP Code backend during startup.
Compatibility is not guaranteed because T3 Code may change its state schema;
the repair helper was tested with T3 Code 0.0.21 state.

If you still need to import `~/.t3/userdata`, launch DP Code for the first
time with:

```bash
DPCODE_IMPORT_T3=1 dpcode
```

If you already imported T3 Code state and the desktop window restarts with a
backend readiness error, run the repair helper:

```bash
dpcode-repair-t3-import
dpcode
```

The repair helper backs up `~/.dpcode/userdata/state.sqlite` before converting
array-shaped OpenCode model options to the object shape expected by DP
Code.

To explicitly create the skip marker before first launch, run:

```bash
dpcode-skip-t3-import
dpcode
```

## Repo layout

- `PKGBUILD`, `.SRCINFO`, `upstream.sha256`: package metadata for `dpcode-bin`
- `scripts/`: shared release-check, PKGBUILD update, and AUR publish helpers
- `.github/workflows/publish-aur.yml`: CI workflow for automated publishing

## Links

- AUR package: https://aur.archlinux.org/packages/dpcode-bin
- Upstream project: https://github.com/Emanuele-web04/dpcode
