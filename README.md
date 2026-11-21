# linux-cachyos-zen3

Automated GitHub Actions build of the **linux-cachyos-bore** kernel optimized for **AMD Zen 3 (`znver3`)** with **Clang ThinLTO** and GPG-signed repository metadata.

## Features
- **Scheduler:** BORE (Burst-Oriented Response Enhancer)
- **Architecture:** `-march=znver3`
- **Compiler:** Clang + ThinLTO
- **Security:** Cryptographically signed packages and database (`Required DatabaseRequired`)
- **Updates:** Automatically checked and built every 12 hours via GitHub Actions

## Installation (Arch Linux / CachyOS)

1. Import and locally sign the repository GPG public key:
   ```bash
   curl -sSL https://github.com/treleas/linux-cachyos-zen3/releases/download/repo/public.gpg | sudo pacman-key --add -
   sudo pacman-key --lsign-key E950B6F558D3451C
   ```

2. Add the repository to `/etc/pacman.conf` (above `[core]` or `[cachyos]`):
   ```ini
   [linux-cachyos-znver3]
   SigLevel = Required DatabaseRequired
   Server = https://github.com/treleas/linux-cachyos-zen3/releases/download/repo
   ```

3. Update package databases and install the kernel:
   ```bash
   sudo pacman -Syu linux-cachyos-zen3 linux-cachyos-zen3-headers
   ```

## License
Built from [CachyOS/linux-cachyos](https://github.com/CachyOS/linux-cachyos). Distributed under the **GPL-2.0** license.
