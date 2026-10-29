# FimawCode 2.4.3

## The sign-in gate's buttons now sign you in

The gate's **Sign in** and **Create an account** buttons opened a page that never signed you in. The
app sent the browser to `https://www.fimaw.com`, and the edge in front of the site answers `www` with
a redirect to `https://fimaw.com` that drops the path and the query string. You landed on the homepage
and nothing happened.

The buttons now open the platform's canonical host, the only host where the handoff link survives:

- **Sign in** &rarr; the platform's sign-in page
- **Create an account** &rarr; the platform's registration page

## A fresh install reaches the gate

- The platform account is read before the local-server resource, so a new install shows the gate
  instead of the recovery screen.
- The window is revealed as soon as the gate is shown, so the startup splash no longer covers it.

## Deployment switches reach the app

- The desktop reads the feature map from the `features` object the platform publishes. Every
  deployment switch was silently dropped before.
- The platform publishes a new `customProviders` switch, off by default: provider management is
  hidden for everyone, and only the providers an administrator assigns through plans remain
  available.

## Website

- The apex `fimaw.com` is the canonical host. The sitemap link and the website label follow it.

## Install (Windows x64)

1. Download `fimawcode-desktop-win-x64-2.4.3.exe` below.
2. Run it. The wizard shows the license, lets you choose the install folder, and offers Desktop and
   Start-menu shortcuts. It installs for the current user, so it never needs an administrator.
3. Start **FimawCode** and sign in, or create an account and pick a plan.

The installer is not code-signed yet, so SmartScreen shows its usual unknown-publisher warning.
Verify the download against `SHA512SUMS` (attached) or `docs/verification.md`.

Linux and macOS builds come from the release pipeline.
