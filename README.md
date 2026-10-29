# FimawCode releases

Packaged **FimawCode** builds: the desktop app with its guided Windows installer, and the `fimawcode`
command for the terminal, for every system we support.

This repository intentionally contains **no source code**. It exists so anyone can download and
install a verified build without access to the source repository. Every binary here is produced by
the release pipeline and published with its checksums.

- Website and downloads: <https://www.fimaw.com/download>
- Documentation: <https://www.fimaw.com/docs>
- Support: <contact@fimaw.com>

## What a release contains

| System | Desktop app | Terminal CLI |
| --- | --- | --- |
| Windows (x64, ARM64) | `fimawcode-desktop-win-<arch>-<version>.exe` — guided installer | `fimawcode-windows-<arch>.zip` |
| macOS (Apple silicon, Intel) | `fimawcode-desktop-mac-<arch>-<version>.dmg` | `fimawcode-darwin-<arch>.zip` |
| Linux (x64, ARM64) | `.AppImage`, `.deb`, `.rpm` | `fimawcode-linux-<arch>.tar.gz` |

Each release also carries `SHA512SUMS`, the version manifest, and third-party notices for the open
source components bundled inside the builds.

## Install

### Windows

1. Download `fimawcode-desktop-win-x64-<version>.exe` (or the `arm64` build on ARM devices).
2. Run it. The wizard shows the license, lets you choose the install folder, and offers Desktop and
   Start-menu shortcuts. It installs for the current user, so it never needs an administrator.
3. Start **FimawCode** and sign in with your FimawCode account, or create one and pick a plan.

Windows SmartScreen can warn about a new publisher until the build is signed by a certificate this
project has not been issued yet. The checksum below is how you confirm the file you downloaded is the
one published here.

### macOS

1. Download `fimawcode-desktop-mac-arm64-<version>.dmg` (Apple silicon) or `mac-x64` (Intel).
2. Open the image and drag FimawCode into Applications.
3. Start it and sign in with your FimawCode account.

### Linux

- **AppImage**: make it executable (`chmod +x fimawcode-desktop-linux-x64-<version>.AppImage`) and run it.
- **Debian and Ubuntu**: `sudo apt install ./fimawcode-desktop-linux-x64-<version>.deb`
- **Fedora and openSUSE**: `sudo rpm -i fimawcode-desktop-linux-x64-<version>.rpm`

### Terminal CLI

```bash
# macOS and Linux, one command
curl -fsSL https://fimaw.com/install | bash

# npm, bun, Homebrew, or mise
npm install -g @fimawcode/cli
brew install FimawLLC/tap/fimawcode
```

Or unpack the archive for your system from this release and put `fimawcode` on your `PATH`.

## Requirements

- **Windows**: Windows 10 22H2 or later, x64 or ARM64.
- **macOS**: macOS 13 or later, Apple silicon or Intel.
- **Linux**: a glibc 2.28+ distribution (or musl), AppImage/FUSE, or the deb/rpm package manager.
- **Account**: FimawCode runs on a FimawCode plan. The desktop app asks you to sign in or subscribe
  on first launch, and a plan decides which providers and hosted models are available to you.

## Verify a download

Every release lists the checksums it published. On macOS or Linux:

```bash
shasum -a 512 -c SHA512SUMS --ignore-missing
```

On Windows:

```powershell
Get-FileHash .\fimawcode-desktop-win-x64-<version>.exe -Algorithm SHA512
```

Compare the result with the matching line of `SHA512SUMS`, and with the checksum posted on
<https://www.fimaw.com/download>. If they differ, delete the file and download it again.

The desktop build is also what the **Check for updates** action inside the app verifies before it
installs anything.

## Privacy and security

- The app keeps your work on your machine. Sessions, files, and credentials stay in your user
  profile unless you connect a provider that sends a request.
- The desktop app talks to the platform only for the things a plan covers: sign-in, the provider
  catalog, hosted model requests, usage, and updates.
- Report a security issue to <contact@fimaw.com> rather than opening a public issue.

## License

The FimawCode distribution includes open source components under their own licenses; see the
third-party notices attached to each release. The FimawCode name and logo are trademarks of
Fimaw LLC.

Copyright © Fimaw LLC.
