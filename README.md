# ExamLockr — Desktop Downloads

Official desktop builds of **ExamLockr**, the secure examination platform used at
Ashesi University.

This repository contains **downloads only**. The application source is private.

## Download

Get the latest version from the [**Releases**](../../releases/latest) page.

| Your computer | File |
|---|---|
| Mac — 2020 or newer (M1–M4) | `ExamLockr-<version>-mac-arm64.dmg` |
| Mac — 2019 or older (Intel) | `ExamLockr-<version>-mac-x64.dmg` |
| Windows — **recommended** | `ExamLockr-Portable-<version>-win-x64.exe` |
| Windows — normal install | `ExamLockr-Setup-<version>-win-x64.exe` |
| Linux — most computers | `ExamLockr-<version>-linux-x86_64.AppImage` |
| Linux — ARM / Raspberry Pi | `ExamLockr-<version>-linux-arm64.AppImage` |

Not sure which Linux build? Run `uname -m`. `x86_64` is the first one,
`aarch64` the second.

## Installing

**Windows** — you may hit two warnings, both expected:

1. **Chrome:** *"…isn't commonly downloaded"* — click the arrow beside the
   download and choose **Keep**. ExamLockr is new, so few people have downloaded
   it yet. That is all the warning means.
2. **Windows:** *"Windows protected your PC"* — click **More info** →
   **Run anyway**.

Then: the **portable** build just runs when you double-click it — no installation
and no admin rights. The **installer** build runs a normal setup wizard.

Do this before your exam starts, not during it.

**macOS** — open the `.dmg` and drag ExamLockr to Applications. On first launch,
right-click the app → **Open** → **Open**.

**Linux** — make the file executable, then run it:

```bash
chmod +x ExamLockr-*.AppImage
./ExamLockr-*.AppImage
```

You can also right-click the file → Properties → Permissions → tick
*"Allow executing file as program"*. If double-clicking does nothing, this step
was missed — the download is not corrupt.

## Why does my computer warn me?

These builds are not yet code-signed, so Windows SmartScreen and macOS Gatekeeper
show a caution the first time you run them. The warnings above explain how to
proceed. Verify your download against `SHA256SUMS.txt`, published with every
release:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

## Support

Problems installing or running the app? Contact your course faculty or the
invigilator before your exam — not during it.
