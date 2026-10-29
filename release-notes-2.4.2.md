FimawCode 2.4.2 — packaged desktop installers and terminal builds.

## Attached in this release

| System | File |
| --- | --- |
| Windows x64 (desktop) | `fimawcode-desktop-win-x64-2.4.2.exe` |

`SHA512SUMS` lists the checksum of every file above. Verify before installing:

```bash
shasum -a 512 -c SHA512SUMS --ignore-missing
```

## What is new in 2.4.2

- **Sign-in gate.** A fresh install now shows a sign-in screen and opens the app only after the
  platform has signed an account in, or after an account is created and a plan is chosen. There is no
  anonymous mode.
- **Plan-controlled providers.** The app reads the plan capabilities and the deployment switches, so
  provider management, workspaces, extensions, and hosted models follow what an administrator allows.
- **New About page** built around the official artwork, with Product, Credits, Legal, and Account
  sections and a sign-out action.
- **Guided Windows installer** with the official header and sidebar art, a license page, an
  install-folder choice, and shortcut options.
- **New default port.** FimawCode now listens on 19881 (19882 for a local checkout), so it can run
  beside OpenCode, which uses 28894.

## Requirements

Windows 10 22H2 or later (x64). A FimawCode account and plan are required to use the app.

## Notes

- The Windows build is not signed yet, so SmartScreen reports an unknown publisher on first run.
  Verify the checksum above; signing is in progress.
- macOS, Linux, and ARM64 builds are produced by the same release pipeline and are added to this
  repository as they become available.

Full documentation: <https://www.fimaw.com/docs> · Downloads: <https://www.fimaw.com/download>
