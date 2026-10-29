# Verifying a download

Every file in a release is published with a SHA-512 checksum in `SHA512SUMS`. Verifying it takes a
few seconds and is the only way to be sure the file you have matches the file we published.

## Checksums

macOS and Linux:

```bash
shasum -a 512 -c SHA512SUMS --ignore-missing
```

Windows PowerShell:

```powershell
Get-FileHash .\fimawcode-desktop-win-x64-<version>.exe -Algorithm SHA512
```

The printed hash must equal the matching line in `SHA512SUMS`. The same hash is shown on
<https://www.fimaw.com/download>.

## Why Windows shows a warning

The Windows installer is not yet signed with an Authenticode certificate issued to Fimaw LLC, so
SmartScreen reports an unknown publisher the first time you run it. That warning means "Windows has
not seen this file before", not "this file is known to be harmful". Verify the checksum above before
you continue.

Code signing is in progress for Windows and macOS; once the certificates are issued, releases will
carry a publisher signature and the warning disappears.

## Automatic updates

The desktop app checks its own update feed and installs updates silently. It verifies the update
before installing it, and an interrupted update never leaves a half-written install: the staged copy
is moved into place only when it is complete.

You can turn updates off in **Settings → General**.

## Reporting a problem

- Product or account help: <contact@fimaw.com>
- Something looks wrong with a published file: <info@fimaw.com> with the file name, the version, and
  the checksum you computed.
- Security issue: <contact@fimaw.com> rather than a public issue, so it can be handled privately.
