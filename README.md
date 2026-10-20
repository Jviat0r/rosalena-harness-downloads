# Rosalena Harness downloads

Installers for **Rosalena Harness**, the desktop app. This repository holds release binaries and
nothing else. The source lives in a private repository.

Every file is attached to a release, not committed here. Check the checksum against what the release
publishes before you run it:

```bash
sha256sum Rosalena-Harness-Setup-0.1.0-x64.exe                   # Windows or Linux
shasum -a 256 Rosalena-Harness-0.1.0-arm64.dmg                   # macOS
certutil -hashfile Rosalena-Harness-Setup-0.1.0-x64.exe SHA256   # Windows cmd
```

## Current release: v0.1.0

| File | Platform |
| --- | --- |
| `Rosalena-Harness-Setup-0.1.0-x64.exe` | Windows 10/11, 64-bit |
| `Rosalena-Harness-0.1.0-x64-portable.exe` | Windows 10/11, 64-bit, no install |
| `Rosalena-Harness-0.1.0-arm64.dmg` | macOS 11 or newer, Apple silicon |
| `Rosalena-Harness-0.1.0-arm64.zip` | macOS 11 or newer, Apple silicon |
| `Rosalena-Harness-0.1.0-x64.dmg` | macOS 11 or newer, Intel |
| `Rosalena-Harness-0.1.0-x64.zip` | macOS 11 or newer, Intel |

Sizes and SHA-256 sums are in the release notes for each tag. The website's `releases.json` is
generated from the files that actually arrived, so a file missing from a release shows up on the site
as missing instead of as a link that 404s.

## macOS: the first launch needs one step

The macOS builds are **unsigned**. There is no Apple Developer certificate behind them, so Gatekeeper
refuses the first launch with "Apple could not verify Rosalena Harness is free of malware".

Two ways past it, both ordinary and both local to your machine:

1. **Right click the app, then Open**, and confirm Open in the dialog. Once per download.
2. **Or one command**, which removes the quarantine flag the download added:

   ```bash
   xattr -dr com.apple.quarantine "/Applications/Rosalena Harness.app"
   ```

Nothing is disabled system-wide, no security setting is changed, and later launches are normal.

## Windows

The installer is not code signed yet either, so SmartScreen may say "Windows protected your PC".
Choose **More info**, then **Run anyway**. The portable `.exe` is the same app in one file: no
installer, no registry entries, no uninstaller.

## What the app is

Rosalena Harness runs a local router and one window in front of it. It talks to cloud models and to
models you run on your own machine. The website's download page has the long version: requirements,
what the app does on first run, and what it does not do.
