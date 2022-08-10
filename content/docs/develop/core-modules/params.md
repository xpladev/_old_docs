---
weight: 110
title: Params
---

# Params

{{< hint info >}}
**Note**  
Xpla's params module inherits from the Cosmos SDK's [`params`](https://docs.cosmos.network/master/modules/params/) module. This document is a stub and covers mainly important Xpla-specific notes about how it is used.
{{< /hint >}}

The params module provides a base parameter store for all other Xpla modules. Structures made with the `params` module are globally available and use subspaces to register specific params to particular modules. The params module defines two types of access: `Keeper` and `Subspace`.

## Params Types

### Keeper

`Keeper` has a permission to access all existing subspaces which are mentioned later on in this document. For example, if a proposal passes through the [governance](/docs/develop/module-specifications/spec-governance.md) the `Keeper` can be routed to modified params automatically and according to the proposal.

### Subspaces

`Subspace` is a unique namespace for a paramstore, where keys are configured with a certain prefix. `Subspace` are used by individual keepers, which require an unmodifiable private parameter store.

## Parameters

The genesis parameters for the mint module outlined in the [Genesis Builder Script](https://github.com/xpladev/genesis-tools/blob/main/src/genesis_builder.py#L112) are as follows:
