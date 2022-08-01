---
weight: 50
title: Sync
---

# Sync

## Before sync

Certain files will need to be absent or deleted prior to download. A quicksync replaces blockchain data with a custom snapshot. For most use cases a "pruned" version is adequate. Pruned versions will have certain transactions removed from the archive to improve node performance. If you are running a node for archival purposes, you will want an `archive` or `default` download.

After choosing the appropriate download type, examine your node and ensure that `.xpla/data` is empty.

**Example**:

```bash
6:22PM INF Removed all blockchain history dir=/home/ubuntu/.xpla/data
```

::: {warning}
If you are a validator, ensure that you do not remove your private key.

Example of a removed private key:

```bash
6:22PM INF Reset private validator file to genesis state keyFile=/home/ubuntu/.xpla/config/priv_validator_key.json stateFile=/home/ubuntu/.xpla/data/priv_validator_state.json
```

:::

If you have an address book downloaded, you may keep it. Otherwise, you will need to download the [appropriate addressbook](join-a-network.md#join-a-public-network) prior to running `xplad start`.

## During sync

After [Joining a public network](join-a-network.md#join-a-public-network), your node will begin to sync.

::: {admonition} Sync start times
:class: caution

Nodes take at least an hour to start syncing. This wait time is normal. Before troubleshooting a sync, please wait an hour for the sync to start.
:::

## Monitor the sync

Your node is catching up with the network by replaying all the transactions from genesis and recreating the blockchain state locally. You can verify this process by checking the `latest_block_height` in the `SyncInfo` of the `xplad status` response:

```json
  {
    "SyncInfo": {
        "latest_block_height": "42", <-----
        "catching_up"        : true
    },
  ...
  }
```

Compare this height to the **Latest Blocks** by checking the API for latest block heights on [Dimension](https://dimension-lcd.xpla.dev/blocks/latest), or [tesseract](https://tesseract-lcd.xpla.dev/blocks/latest) to see your progress.

## State sync

You can significantly accelerate the synchronization process by providing `xplad` with a recent snapshot of the network state. Snapshots are made publicly available by members of the Xpla community one example can be downloaded from [Polkachu - Dimension Mainnet](https://polkachu.com/state_sync/xpla). [Polkachu - tesseract Testnet](https://polkachu.com/testnets/xplaInstructions) are provided by Polkachu, and not maintained as part of this documentation.

## Sync complete

You can tell that your node is in sync with the network when `SyncInfo.catching_up` in the `xplad status` response returns `false` and the `latest_block_height` corresponds to the public network blockheight found on the API for either [Dimension](https://dimension-lcd.xpla.dev/blocks/latest), or [tesseract](https://tesseract-lcd.xpla.dev/blocks/latest).

```bash
xplad status
```

**Example**:

```json
  {
    "SyncInfo": {
        "latest_block_height": "7356350",
        "catching_up"        : false
    },
  ...
  }
```

Validators can view the status of the network using [Xpla Finder](https://finder.c2x.world).

## Sync faster during testing

Sometimes you may want to sync faster by foregoing checks. This command should only be used by advanced users in non-production environments. To speed up the sync process during testing, use the following command:

```bash
xplad start --x-crisis-skip-assert-invariants
```

## Congratulations!

You've successfully joined a network as a full node operator. If you are a validator, continue to [manage a Xpla validator](../manage-a-validator/_index.md) for the next steps.
