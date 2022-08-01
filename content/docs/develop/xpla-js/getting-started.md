# Get started with xpla.js

This is an in-depth guide on how to use the `xpla.js` SDK.

In this tutorial, you'll learn how to:

1. [Set up your project](#1-set-up-your-project)
2. [Set up a Xpla LCD (light client daemon)](#2-initialize-the-lcd)
3. [Create and connect a wallet](#3-create-a-tesseract-testnet-wallet)
4. [Query a swap contract](#5-query-a-xplaswap-contract-and-set-up-the-transaction)
5. [Create, sign, and broadcast a transaction](#6-broadcast-the-transaction)

By the end of this guide, you'll be able to execute a token swap from your application using xpla.js.

## Prerequisites

- [npm and node.js](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- Xpla Station browser extension

## 1. Set up your project

1. Create a new directory for your project:

   ```sh
   mkdir my-xpla-js-project

   ```

2. Enter your new project directory:

   ```sh
   cd <my-xpla-js-project>
   ```

3. Next, initialize npm, install the `xpla.js` package, and create an `index.js` file to house the code:

   ```sh
   npm init -y
   npm install @c2xdev/xpla.js
   touch index.js
   ```

4. Open the `package.json` file in a code editor and add `"type": "module",`.

   ```json
   {
     // ...
     "type": "module"
     // ...
   }
   ```

## 2. Initialize the LCD

Xpla’s LCD or Light Client Daemon allows users to connect to the blockchain, make queries, create wallets, and submit transactions. It's the main workhorse behind `xpla.js`.

1. Install a fetch library to make HTTP requests and dynamically pull recommended gas prices. You can use the one referenced below or choose your favorite.

   ```sh
   npm install --save isomorphic-fetch
   ```

2. Open your `index.js` file in a code editor and input the following to initialize the LCD:

   ```ts
   import fetch from "isomorphic-fetch";
   import { Coins, LCDClient } from "@c2xdev/xpla.js";
   const gasPrices = await fetch(
     "https://tesseract-api.xpla.dev/gas-prices", { redirect: 'follow' }
   );
   const gasPricesJson = await gasPrices.json();
   const gasPricesCoins = new Coins(gasPricesJson);
   const lcd = new LCDClient({
     URL: "https://tesseract-lcd.xpla.dev", // Use "https://dimension-lcd.xpla.dev" for prod
     chainID: "tesseract-1", // Use "dimension-1" for production
     gasPrices: gasPricesCoins,
     gasAdjustment: "1.5", // Increase gas price slightly so transactions go through smoothly.
     gas: 10000000,
   });
   ```

   ::: {admonition} Switching to the mainnet
   :class: note

   The previous code block shows how to connect to the tesseract testnet. To connect to the dimension-1 mainnet for production, use “`https://dimension-lcd.xpla.dev`”.

   You will also need to change the `chainID` from `"tesseract-1"` to `"dimension-1"`.
   :::

## 3. Create a tesseract testnet wallet

1. You'll need a wallet to sign and submit transactions. [Create a new wallet](../../learn/station/download/xpla-station-extension.md) using the Xpla Station extension. Be sure to save your mnemonic key!

2. After creating your wallet, you’ll need to set it to use the testnet. Click the gear icon in the extension and change the network from `mainnet` to `testnet`.

3. Add the following code to your `index.js` file and input your mnemonic key:

   ```ts
   import { MnemonicKey } from "@c2xdev/xpla.js";
   const mk = new MnemonicKey({
     mnemonic: " //Input your 24-word mnemonic key here//",
   });
   const wallet = lcd.wallet(mk);
   ```

   :::{admonition} Mnemonic security
   :class: warning

   Although this tutorial has you input your mnemonic directly, this practice should be avoided in production.
   For security reasons, it's better to store your mnemonic key data in your environment by using `process.env.SECRET_MNEMONIC` or `process.env.SECRET_PRIV_KEY`. This practice is more secure than a hard-coded string.

   :::

4. Request testnet funds for your wallet by navigating to the [Xpla faucet](https://faucet.c2x.world) and inputting your wallet address. You'll need these funds to perform swaps and pay for gas fees. Once the funds are in your wallet, you’re ready to move on to the next step.

## 4. Find a contract address

To find the contract address for a specific Xplaswap pair, visit https://app.xplaswap.io/

## 5. Query a Xplaswap contract and set up the transaction

Before you can perform a swap, you’ll need a belief price. You can calculate the belief price of one token by querying the proportion of the two pooled tokens. The belief price +/- the `max_spread` is the range of possible acceptable prices for this swap.

1. Add the following code to your `index.js` file. Make sure the contract address is correct.

   ```ts
   const pool = "<INSERT_POOL_ADDRESS>"; // A xplaswap contract address on tesseract.
   const { assets } = await lcd.wasm.contractQuery(pool, { pool: {} }); // Fetch the amount of each asset in the pool.
   const beliefPrice = (assets[0].amount / assets[1].amount).toFixed(18); // Calculate belief price using proportion of pool balances.
   ```

2. Next, generate a message to broadcast to the network:

   ```ts
   import { MsgExecuteContract } from "@c2xdev/xpla.js";
   const xplaSwap = new MsgExecuteContract(
     wallet.key.accAddress,
     pool,
     {
       swap: {
         max_spread: "0.001",
         offer_asset: {
           info: {
             native_token: {
               denom: "axpla",
             },
           },
           amount: "100000000000",
         },
         belief_price: beliefPrice,
       },
     },
     new Coins({ axpla: "100000000000" })
   );
   ```

## 6. Broadcast the transaction

1. Add the following code to `index.js` to create, sign, and broadcast the transaction. It's important to specify `axpla` as the fee denomination because XPLA is the only denomination the faucet sends.

   ```ts
   const tx = await wallet.createAndSignTx({
     msgs: [xplaSwap],
     feeDenoms: ["axpla"],
   });
   const result = await lcd.tx.broadcast(tx);
   console.log(result);
   ```

2. Run the code in your terminal:

   ```sh
   node index.js
   ```

If successful, you'll see a log of the successful transaction and some new tokens in your wallet.

And that's it! You can find other pool addresses [here](https://app.xplaswap.io/) to call other swaps. Be sure to use the correct testnet or mainnet contract address.

## More examples

View the [Common examples](common-examples.md) section for more information on using xpla.js.
