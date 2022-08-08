---
weight: 20
title: Contracts
---

# Contract

Smart contracts are an advanced feature of Xpla wallet. If you’re using Xpla wallet for the first time, follow the [Xpla wallet tutorial]({{< ref "wallet" >}}).

## Prerequisites

Compile a contract locally and create a `.wasm` file.

## Upload

Deploy a contract by uploading your `.wasm` file to Xpla wallet.

1. Open Xpla wallet and connect your wallet. Click **Contracts**.

2. Click **Upload**.

3. Upload your `.wasm` file and enter your password.

4. Click **Submit**. 

Your contract is now uploaded, and you received a contract code ID.

## Instantiate

Use **Create** to initialize your contract after uploading.

1. Click **Create**.

2. Enter your contract code ID, `InitMsg JSON`, name, and description.

3. Confirm the fee amounts and enter your password. Click **Submit**.

Your contract is now initialized.

## Query

Use **Query** to find out contract values. Querying does not cost anything.

1. Click **Query** located under your contract address.

2. Enter your `HandleMsg JSON`. Click **Next**.

Xpla wallet will show your query result.

## Interact

Use **Interact** to use the contract. Interacting will spend gas.

1. Click **Interact** located under your contract address.

2. Enter your `HandleMsg JSON`. Click **Next**.

3. Confirm the fee amounts and enter your password. Click **Interact**.
