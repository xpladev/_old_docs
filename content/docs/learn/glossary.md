---
weight: 50
title: Glossary
---

# Glossary

Use this glossary to learn about terms specific to the Xpla Protocol.

## Active Set

The top 8 [validators]({{< ref "#validator" >}}) that participate in consensus, receive rewards, and secure the blockchain.

## Blockchain

An unchangeable ledger of transactions copied among a network of independent computer systems.

## Blocks

Groups of information stored on a [blockchain](#blockchain). Each block contains transactions that are grouped, verified, and signed by validators.

## Bonded validator

A [validator]({{< ref "#validator" >}}) in the [active set]({{< ref "#active-set" >}}) participating in consensus. Bonded validators earn [rewards]({{< ref "#rewards" >}}).

## Bonding

When a user [delegates]({{< ref "#delegate" >}}) or bonds XPLA to a [validator]({{< ref "#validator" >}}) to receive [staking rewards]({{< ref "#rewards" >}}). Validators never have ownership of a delegator's [XPLA]({{< ref "#xpla" >}}), even when bonded. Delegating, bonding, and staking generally refer to the same process.

## Commission

The percentage of [staking rewards]({{< ref "#rewards" >}}) a [validator]({{< ref "#validator" >}}) keeps before distributing the rest of the rewards to [delegators]({{< ref "#delegator" >}}). Commission is a validator’s income. Validators set their own commission rates.

## Community Pool

A special fund designated for funding community projects. Any community member can create a governance proposal to spend the tokens in the community pool. If the proposal passes, the funds are spent as specified in the proposal.

## Consensus

A system used by [validators]({{< ref "#validator" >}}) to agree that each [block]({{< ref "#blocks" >}}) of transactions in a [blockchain]({{< ref "#blockchain" >}}) is correct. The Xpla blockchain uses the Tendermint consensus. Validators earn [rewards]({{< ref "#rewards" >}}) for participating in consensus. Visit the [Tendermint official documentation site](https://docs.tendermint.com/) for more information.

## Cosmos-SDK

The open-source framework the Xpla blockchain is built on. For more information, check out the [Cosmos SDK Documentation](https://docs.cosmos.network/).

## dApp

An application built on a decentralized platform.

## DDoS

Distributed denial of service attack. When an attacker floods a network with traffic or requests in order to disrupt service.

## DeFi

Decentralized finance. A movement away from traditional finance and toward systems that do not require financial intermediaries.

## Delegate

When users or delegators add their [XPLA]({{< ref "#xpla" >}}) to a [validator]({{< ref "#validator" >}})'s stake in exchange for rewards. Delegated XPLA is bonded to a validator. Validators never have ownership of a [delegator]({{< ref "#delegator" >}})'s XPLA. Delegating, bonding, and staking generally refer to the same process.

## Delegator

A user who [delegates]({{< ref "#delegate" >}}), bonds, or stakes [XPLA]({{< ref "#xpla" >}}) to a [validator]({{< ref "#validator" >}}) to earn [rewards]({{< ref "#rewards" >}}). Delegating, bonding, and staking generally refer to the same process.

## Fees

- **Gas**: Compute fees added on to all transactions to avoid spamming. [Validators]({{< ref "#validator" >}}) set minimum gas prices and reject transactions that have implied gas prices below this threshold.

For more information on fees, visit [Fees]({{< ref "fees" >}}).

## Full Node

A computer connected to the [Xpla mainnet]({{< ref "#mainnet" >}}) that is able to validate transactions and interact with the Xpla blockchain. All active [validators]({{< ref "#validator" >}}) run full nodes.

## XPLA

The native staking token of the Xpla protocol. XPLA is also used as a governance token. [Delegators]({{< ref "#delegator" >}}) can stake XPLA to receive rewards.

## Governance

Governance is the democratic process that allows users and [validators]({{< ref "#validator" >}}) to make changes to the Xpla protocol. Community members submit, vote, and implement proposals. One staked [XPLA]({{< ref "#xpla" >}}) is equal to one vote.

## Governance Proposal

A written submission for a change or addition to the Xpla blockchain. Topics of proposals can vary from community pool spending, software changes, or parameter changes.

## IBC

Inter-Blockchain Communication. The technology that enables different [blockchains]({{< ref "#blockchain" >}}) to interact with each other. IBC allows for assets to be traded and transacted across different blockchains.

## Inactive Set

[Validators]({{< ref "#validator" >}}) that are not in the [active set]({{< ref "#active-set" >}}). These validators do not participate in [consensus]({{< ref "#consensus" >}}) and do not earn [rewards]({{< ref "#rewards" >}}).

## Jailed

Validators who misbehave are jailed or excluded from the [active set]({{< ref "#active-set" >}}) for a period amount of time.

## Miss

When a vote fails to be included in consensus.

## Module

A section of the Xpla core that represents a particular function of the Xpla protocol. Visit the [Xpla core module specifications]({{< ref "core-modules" >}}) for more information.

## Dimension-1

The latest version of the [mainnet]({{< ref "#mainnet" >}})

## Pools

Groups of tokens. Supply pools represent the total supply of tokens in a market.

## Proof of Stake

Proof of Stake. A style of blockchain where validators are chosen to propose blocks according to the number of coins they hold.

## Quorum

The minimum amount of votes needed to make an election viable. 40% of all staked XPLA must vote to meet quorum. If quorum is not met before the voting period ends, the proposal fails, and the proposer's deposit is burned.

## Redelegate

When a delegator wants to transfer their bonded XPLA to a different validator. Redelegating XPLA is instant and does not require a 21-day unbonding period.

## Rewards

Revenue generated from fees given to validators and disbursed to delegators.

## Self-delegation

The amount of XPLA a validator bonds to themselves. Also referred to as self-bond.

## Slashing

Punishment for validators that misbehave. Validators lose part of their stake when they get slashed.

For more information, see [slashing]({{< ref "about-xpla#slashing" >}}) in the description of the Xpla protocol.

## Slippage

The difference in a coin's price between the start and end of a transaction.

## Stake

The amount of [XPLA]({{< ref "#xpla" >}}) bonded to a validator.

## Staking

When a user delegates or bonds their XPLA to an active validator to receive rewards. Bonded XPLA adds to a validator's stake. Validators provide their stakes as collateral to participate in the consensus process. Validators with larger stakes are chosen to participate more often. Validators receive staking rewards for their participation. A validator's stake can be slashed if the validator misbehaves. Validators never have ownership of a delegator's XPLA, even when staking.

For more information on staking, visit the [concepts page]({{< ref "about-xpla#staking" >}}).

## Tendermint Consensus

The consensus procedure used by the Xpla protocol. First, a validator proposes a new block. Other validators vote on the block in two rounds. If a block receives a two-thirds majority or greater of yes votes in both rounds, it gets added to the blockchain. Validators get rewarded with the block's transaction fees. Proposers get rewarded extra. Each validator is chosen to propose based on their weight. Check out the [Tendermint official documentation](https://docs.tendermint.com/) for more information.

## Xpla Core

The official source code for the Xpla protocol.

For more information on the Xpla core, see [Xpla Core Modules]({{< ref "core-modules" >}}).

## Mainnet

The Xpla protocol's blockchain network where all transactions take place.

## Xpla Vault

Xpla's native wallet and platform for swaps, governance, and staking. In Xpla Vault, you can send, receive, and stake Xpla coins. You can also participate in governance and vote on proposals.

To learn how to install and get started using Xpla Vault, visit the [Xpla Vault tutorial]({{< ref "xpla-vault/download" >}}).

To learn how to use the advanced features of Xpla Vault, visit the [Xpla Vault how-to guide]({{< ref "xpla-vault/wallet" >}}).

## xplad

The command line interface for interacting with a Xpla node.

For more information on xplad, see [`xplad` guides]({{< ref "xplad" >}}).

## Xplavaloper Address

A validator's public address beginning with `xplavaloper` followed by a string of characters.

## Testnet

A version of the mainnet just for testing. The testnet does not use real coins. You can use the testnet to get familiar with transactions. The current testnet for Xpla is [`tesseract-1`]({{< ref "public-and-private-endpoints" >}})

## The Xpla Ecosystem

A quickly expanding network of decentralized applications built on the Xpla protocol.

## Tombstone

To block a validator from participating in consensus. Tombstoned validators cannot rejoin the active set.

## Total Stake

The total amount of XPLA bonded to a delegator, including self-bonded XPLA.

## Unbonded Validator

A validator that is not in the active set and does not participate in consensus or receive rewards. Some unbonded validators may be jailed.

## Unbonding Validator

A validator transitioning from the active set to the inactive set. An unbonding validator does not participate in consensus or earn rewards. The unbonding process takes 21 days.

## Unbonded XPLA

XPLA that can be freely traded and is not staked to a validator.

## Unbonding

When a delegator decides to undelegate their XPLA from a validator. This process takes 21 days. No rewards accrue during this period. This action cannot be stopped once executed.

## Unbonding XPLA

[XPLA]({{< ref "#xpla" >}}) that is transitioning from bonded to unbonded. XPLA that is unbonding cannot be traded freely. The unbonding process takes 21 days. No rewards accrue during this period. This action cannot be stopped once executed.

## Undelegate

When a [delegator]({{< ref "#delegator" >}}) no longer wants to have their XPLA bonded to a validator. This process takes 21 days. No rewards accrue during this period. This action cannot be stopped once executed.

## Uptime

The amount of time a [validator]({{< ref "#validator" >}}) is active in a given timeframe. Validators with low up time may be [slashed]({{< ref "#slashing" >}}).

## Validator

A Xpla blockchain miner responsible for verifying transactions on the blockchain. Validators run programs called full nodes that allow them to participate in consensus, verify blocks, participate in governance, and receive rewards. The top 130 validators with the highest total stake can participate in consensus.

For more information on validators, visit the [concepts page]({{< ref "about-xpla#validators" >}}).

## Weight

The measure of a [validator's]({{< ref "#validator" >}}) total stake. Validators with higher weights get selected more often to propose blocks. A validator's weight is also a measure of their voting power in [governance]({{< ref "#governance" >}}).
