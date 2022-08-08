---
weight: 60
title: Restore A Validator
---

# Restore a Validator

A validator can be completely restored on a new Xpla node with the following set of keys:

- The Consensus key, stored in `~/.xpla/config/priv_validator.json`
- The mnemonic to the validator wallet

{{< hint danger >}}
**Danger**  
Before proceeding, ensure that the existing validator is not active. Double voting has severe slashing consequences.
{{< /hint >}}

To Restore a Validator:

1. Setup a full Xpla node synced up to the latest block.
2. Replace the `~/.xpla/config/priv_validator.json` file of the new node with the associated file from the old node, then restart your node.
