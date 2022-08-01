# Fees

```ts
import { Fee } from '@c2xdev/xpla.js';

const msgs = [ new MsgSend( ... ), new MsgExecuteContract( ... ), ]; // messages
const fee = new Fee(50000, { axpla: 4500000 });

const tx = await wallet.createAndSignTx({ msgs, fee });
```

## Automatic fee estimation

If you don't specify a fee when you create your transaction, it will automatically be estimated by simulating it within the node.

```ts
const tx = await wallet.createAndSignTx({ msgs });
```

You can define the fee estimation parameters when you create your `LCDClient` instance. The defaults are:

```ts
const xpla = new LCDClient({
  URL: "https://dimension-lcd.xpla.dev",
  chainID: "dimension-1",
  gasPrices: { axpla: 0.015 },
  gasAdjustment: 1.4,
});
```

You can override these settings by passing the fee estimation parameters in `wallet.createTx` or `wallet.createAndSignTx`:

```ts
const tx = await wallet.createAndSignTx({
  msgs,
  gasPrices: { axpla: 0.01 },
  gasAdjustment: 1.9,
});
```
