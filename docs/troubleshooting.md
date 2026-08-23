# Troubleshooting

Common problems, and what to do about them. If your exam is starting soon,
tell your invigilator first — do not spend the exam window debugging.

## Downloading

**Chrome says the file "isn't commonly downloaded".**
Click the arrow beside the download and choose **Keep**. ExamLockr is new, so
few people have downloaded it yet. That is all the warning means.

**Which file do I need?**

| Your computer | File |
|---|---|
| Mac, 2020 or newer (M1–M4) | `ExamLockr-<version>-mac-arm64.dmg` |
| Mac, 2019 or older (Intel) | `ExamLockr-<version>-mac-x64.dmg` |
| Windows — recommended | `ExamLockr-Portable-<version>-win-x64.exe` |
| Windows — normal install | `ExamLockr-Setup-<version>-win-x64.exe` |
| Linux, most computers | `ExamLockr-<version>-linux-x86_64.AppImage` |
| Linux, ARM devices | `ExamLockr-<version>-linux-arm64.AppImage` |

On Linux, run `uname -m`: `x86_64` is the first one, `aarch64` the second.

## Installing

**Windows: "Windows protected your PC".**
Click **More info**, then **Run anyway**. The app is not yet code-signed, which
is what triggers this. It is not a sign that anything is wrong with the file.

**Windows: nothing seems to happen.**
Use the **Portable** build. It runs straight from the file with no
installation and no administrator rights.

**macOS: "unidentified developer" or "cannot be opened".**
Right-click (or Control-click) the app, choose **Open**, then **Open** again in
the dialog. You only have to do this once.

**macOS: "the application is damaged".**
This is the same cause. If right-click → Open does not clear it, run:

```bash
xattr -cr /Applications/ExamLockr.app
```

**Linux: double-clicking does nothing.**
The file is not marked executable yet. Either:

```bash
chmod +x ExamLockr-*.AppImage
./ExamLockr-*.AppImage
```

or right-click the file → **Properties** → **Permissions** → tick *Allow
executing file as program*. The download is not corrupt.

**Checking your download.** Every release publishes `SHA256SUMS.txt`:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

## Signing in

**"Invalid credentials".** Check the email and password. If you have forgotten
your password, ask your faculty or an invigilator to issue a temporary one —
there is no self-service reset, by design.

**"Could not reach the ExamLockr server".** Your device is offline, or the
server is briefly waking up. Wait a few seconds and try again.

**You were given a temporary password.** You will be asked to set your own
before you can continue. That is expected.

**Students cannot sign in on the website.** Correct — students must use the
desktop app. Faculty and proctors use the browser.

## During an exam

**Do my answers save?** Yes, continuously. Every keystroke and selection is
saved on your own device immediately, and synced to the server moments later.
The indicator near the top says *Saved*, *Saving*, or *Saved on this device*
if you are offline. There is no per-question submit button — only **Finish
exam** on the last question.

**My internet dropped.** Keep working. Answers are stored on your device and
sent automatically when the connection returns. The banner tells you when you
are offline.

**I need to refresh.** Press **Ctrl+R** (or **F5**). This reloads the exam
without leaving the lockdown, and your answers are restored.

**I cannot see the clock or my battery.** They are in the top-right corner of
the exam window. Your normal taskbar or menu bar is hidden during the exam.

**The question panel is too narrow.** Drag the divider between the question and
your answer. Double-click it to reset it to the middle.

**The timer says "Paused by invigilator".** Your invigilator has paused the
exam for everyone. Your time is not running down. Wait for it to resume.

**I need help.** Use the **Request help** button. A proctor will reply, and the
reply appears on your screen as a message you have to acknowledge.

**Can I change the colours?** Yes. The **Theme** control offers several
schemes, light and dark. All of them are checked for readability.

**I finished early.** Use **Leave exam**. You will be asked for a reason. Your
answers are submitted as they stand.

## Things that end an exam

**"Your exam was ended by the invigilator."** Your attempt has been submitted
with whatever you had written. Speak to your invigilator.

**Locked out after repeated warnings.** The lockdown system ends an exam after
repeated integrity violations, such as leaving fullscreen. If this was a
mistake, your faculty can reopen the exam for you.

**Time ran out.** The exam submits automatically. Anything you had written is
included.

## Still stuck

Contact your course faculty or the invigilator. Tell them:

- which file you downloaded and your operating system
- the exact wording of any message
- what you were doing when it happened
