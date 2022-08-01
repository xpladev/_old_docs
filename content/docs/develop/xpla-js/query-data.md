# Query data

After you're connected to the blockchain via an `LCDClient` instance, you can query data from it. Data access is organized into various module APIs, which are accessible from within the `LCDClient` instance. Because they make HTTP requests in the background, they are Promises that can be awaited in order to not block during network IO.

Each module has its own set of querying functions. To get a comprehensive list, explore the module documentation:

- [`auth`](https://c2xdev.github.io/xpla.js/classes/AuthAPI.html)
- [`bank`](https://c2xdev.github.io/xpla.js/classes/BankAPI.html)
- [`distribution`](https://c2xdev.github.io/xpla.js/classes/DistributionAPI.html)
- [`gov`](https://c2xdev.github.io/xpla.js/classes/GovAPI.html)
- [`mint`](https://c2xdev.github.io/xpla.js/classes/MintAPI.html)
- [`msgauth`](https://c2xdev.github.io/xpla.js/classes/MsgAuthAPI.html)
- [`slashing`](https://c2xdev.github.io/xpla.js/classes/SlashingAPI.html)
- [`staking`](https://c2xdev.github.io/xpla.js/classes/StakingAPI.html)
- [`supply`](https://c2xdev.github.io/xpla.js/classes/SupplyAPI.html)
- [`tendermint`](https://c2xdev.github.io/xpla.js/classes/TendermintAPI.html)
- [`tx`](https://c2xdev.github.io/xpla.js/classes/TxAPI.html)
- [`wasm`](https://c2xdev.github.io/xpla.js/classes/WasmAPI.html)
