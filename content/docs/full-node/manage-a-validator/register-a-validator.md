---
weight: 40
title: Register a Validator
---

# Register a Validator

This is a detailed step-by-step guide for setting up a Xpla validator. Please be aware that while it is easy to set up a rudimentary validating node, running a production-quality validator node with a robust architecture and security features requires an extensive setup.

For more information on setting up a validator, see [additional resources]({{< ref "manage-a-validator#additional-resources" >}}).

## Prerequisites

- You have completed [how to run a full Xpla node]({{< ref "run-a-full-xpla-node" >}}), which outlines how to install, connect, and configure a node.
- You are familiar with [xplad]({{< ref "/docs/develop/tools/xplad" >}}).
- You have read through [the validator FAQ]({{< ref "validator-faq" >}})
- You understand the [different keys]({{< ref "validator-faq#validator-keys-and-states" >}}) of a validator in the FAQ

## 1. Retrieve Your PubKey

The Consensus PubKey of your node is required to create a new validator. Run:

```bash
--pubkey=$(xplad tendermint show-validator)
```

## 2. Create a New Validator

   {{< hint info >}}
   **Get tokens**  
   In order for xplad to recognize a wallet address it must contain tokens. For the testnet, use [the faucet](https://faucet.xpla.io/) to send XPLA to your wallet. If you are on mainnet, send funds from an existing wallet. 1-3 XPLA are sufficient for most setup processes.
   {{< /hint >}}

To create the validator and initialize it with a self-delegation, run the following command. `key-name` is the name of the Application Operator Key that is used to sign transactions.

```bash
xplad tx staking create-validator \
    --amount=5000000000000000000axpla \
    --pubkey=$(<your-consensus-PubKey>) \
    --moniker="<your-moniker>" \
    --chain-id=<chain_id> \
    --from=<key-name> \
    --commission-rate="0.10" \
    --commission-max-rate="0.20" \
    --commission-max-change-rate="0.01" \
    --min-self-delegation="1"
```

{{< hint warning >}}
**Warning**  
When you specify commission parameters, the `commission-max-change-rate` is measured as a percentage-point change of the `commission-rate`. For example, a change from 1% to 2% is a 100% rate increase, but the `commission-max-change-rate` is measured as 1%.
{{< /hint >}}

## 3. Confirm Your Validator is Active

If running the following command returns something, your validator is active:

```bash
xplad query tendermint-validator-set | grep "$(xplad tendermint show-validator)"
```

You are looking for the `bech32` encoded `address` in the `~/.xpla/config/priv_validator.json` file.

{{< hint info >}}
**Note**  
Only the top 8 validators in voting power are included in the active validator set.
{{< /hint >}}

## 4. Secure Your Keys and Have a Backup Plan

Protecting and having a contingency backup plan for your [keys]({{< ref "validator-faq#what-type-of-key-do-i-need-to-use" >}}) will help mitigate catastrophic hardware or software failures of the node.
It is a good practice to test your backup plan on a testnet node in case of node failure.
