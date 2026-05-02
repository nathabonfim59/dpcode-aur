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

## Repo layout

- `PKGBUILD`, `.SRCINFO`, `upstream.sha256`: package metadata for `dpcode-bin`
- `scripts/`: shared release-check, PKGBUILD update, and AUR publish helpers
- `.github/workflows/publish-aur.yml`: CI workflow for automated publishing

## Links

- AUR package: https://aur.archlinux.org/packages/dpcode-bin
- Upstream project: https://github.com/Emanuele-web04/dpcode
