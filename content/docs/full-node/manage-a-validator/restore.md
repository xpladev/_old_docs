# Restore a validator

A validator can be completely restored on a new Xpla node with the following set of keys:

- The Consensus key, stored in `~/.xpla/config/priv_validator.json`
- The mnemonic to the validator wallet

::: {danger}
Before proceeding, ensure that the existing validator is not active. Double voting has severe slashing consequences.
:::

To restore a validator:

1. Setup a full Xpla node synced up to the latest block.
2. Replace the `~/.xpla/config/priv_validator.json` file of the new node with the associated file from the old node, then restart your node.