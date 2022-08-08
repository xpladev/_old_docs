---
bookCollapseSection: true
bookFlatSection: false
weight: 20
title: Manage a Validator
---

# Manage a Validator

The tasks in this section describe how to set up a Xpla validator. While setting up a rudimentary validating node is easy, running a production-quality validator node with a robust architecture and security features requires an extensive setup.

The Xpla core is powered by the Tendermint consensus. Validators run full nodes, participate in consensus by broadcasting votes, commit new blocks to the blockchain, and participate in governance of the blockchain. Validators can cast votes on behalf of their delegators. A validator's voting power is weighted according to their total stake. The top 130 validators make up the **Active Validator Set** and are the only validators that sign blocks and receive revenue.

Validators and their delegators earn the following rewards:

- [Gas]({{< ref "/docs/learn/fees#gas" >}}): Fees added on to each transaction to avoid spamming and pay for computing power. Validators set minimum gas prices and reject transactions that have implied gas prices below this threshold.

- [FIXME!! Inflation rewards]({{< ref "/docs/develop/core-modules/mint" >}}): Every block, new XPLA is minted and released to validators and delegators as staking rewards. The rate for the minting of this new XPLA is fixed at 7% per year. 

Validators can set commissions on the fees they receive as an additional incentive.

If validators double sign, are frequently offline, or do not participate in governance, their staked XPLA (including XPLA of users that delegated to them) can be slashed. Penalties can vary depending on the severity of the violation.

For more general information on validators, visit the [validator section]({{< ref "about-xpla#validators" >}}) of the concepts page.

## Additional Resources

- [The validator FAQ]({{< ref "validator-faq" >}})
