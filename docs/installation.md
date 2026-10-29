# Installing FimawCode

Every download on this page comes from a published release of this repository. Pick your system,
verify the checksum, and install.

## Windows

The desktop build ships as a guided installer, not a background one-click install, so you can see
what it does before it does it.

1. Download `fimawcode-desktop-win-x64-<version>.exe` (or `arm64` on an ARM device).
2. Double-click it. The wizard walks through:
   - the license,
   - the folder to install into (defaults to your user profile, so no administrator is required),
   - Desktop and Start-menu shortcuts,
   - the choice to start FimawCode when the wizard finishes.
3. Start FimawCode from the shortcut and sign in.

Updating: the app checks for updates on its own and installs them silently, so an update never
reopens the wizard.

Uninstalling: **Settings → Apps → Installed apps → FimawCode → Uninstall**, or the uninstaller in the
install folder. Your sessions and settings stay in your user profile so a reinstall keeps them.

## macOS

1. Download `fimawcode-desktop-mac-arm64-<version>.dmg` for Apple silicon, or
   `fimawcode-desktop-mac-x64-<version>.dmg` for Intel Macs.
2. Open the image, drag **FimawCode** into **Applications**, and eject the image.
3. Open FimawCode from Applications. If Gatekeeper objects to the publisher, allow it in
   **System Settings → Privacy & Security → Open Anyway**.

## Linux

### AppImage

```bash
chmod +x fimawcode-desktop-linux-x64-<version>.AppImage
./fimawcode-desktop-linux-x64-<version>.AppImage
```

### Debian, Ubuntu, and derivatives

```bash
sudo apt install ./fimawcode-desktop-linux-x64-<version>.deb
```

### Fedora, RHEL, and openSUSE

```bash
sudo rpm -i fimawcode-desktop-linux-x64-<version>.rpm
```

## Terminal

```bash
curl -fsSL https://fimaw.com/install | bash
```

The installer places `fimawcode` in `$HOME/.fimawcode/bin` and picks the native binary for your
platform. Package managers work too:

```bash
npm install -g @fimawcode/cli
bun install -g --trust @fimawcode/cli
brew install FimawLLC/tap/fimawcode
mise use -g fimawcode
```

## First launch

FimawCode runs on a FimawCode plan, so the desktop app asks you to sign in or to create an account
and choose a plan before it opens. The sign-in happens in your browser and returns to the app
through a `fimawcode://` link; the app then unlocks itself. There is no anonymous mode.

Your plan decides what you can connect: an administrator controls which providers and hosted models
appear, and whether you may add your own provider keys. A deployment can hide hosted models entirely.

## Pairing your phone or another device

Run `fimawcode pair` in a project directory, then open the printed link on the other device. The link
works once and expires shortly after it is printed.

## Where your data lives

| What | Where |
| --- | --- |
| Sessions, configuration, logs | `~/.local/share/fimawcode`, `%LOCALAPPDATA%` on Windows |
| Desktop settings and window state | the app's user-profile directory |
| Account session | the desktop's own store, readable only by your user account |

Removing the app does not remove your sessions; delete the directories above if you want them gone.
