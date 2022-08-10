---
weight: 120
title: Query Data
---

# Query Data

After you're connected to the blockchain via an `LCDClient` instance, you can query data from it. Data access is organized into various module APIs, which are accessible from within the `LCDClient` instance. Because they make HTTP requests in the background, they are Promises that can be awaited in order to not block during network IO.

Each module has its own set of querying functions. To get a comprehensive list, explore the module documentation:

- [`auth`](https://xpladev.github.io/xpla.js/classes/AuthAPI.html)
- [`bank`](https://xpladev.github.io/xpla.js/classes/BankAPI.html)
- [`distribution`](https://xpladev.github.io/xpla.js/classes/DistributionAPI.html)
- [`gov`](https://xpladev.github.io/xpla.js/classes/GovAPI.html)
- [`mint`](https://xpladev.github.io/xpla.js/classes/MintAPI.html)
- [`msgauth`](https://xpladev.github.io/xpla.js/classes/MsgAuthAPI.html)
- [`slashing`](https://xpladev.github.io/xpla.js/classes/SlashingAPI.html)
- [`staking`](https://xpladev.github.io/xpla.js/classes/StakingAPI.html)
- [`supply`](https://xpladev.github.io/xpla.js/classes/SupplyAPI.html)
- [`tendermint`](https://xpladev.github.io/xpla.js/classes/TendermintAPI.html)
- [`tx`](https://xpladev.github.io/xpla.js/classes/TxAPI.html)
- [`wasm`](https://xpladev.github.io/xpla.js/classes/WasmAPI.html)
