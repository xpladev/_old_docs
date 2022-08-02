---
weight: 80
title: Make a Connection
---

# Make a Connection

Users can interact with the blockchain by using the following modes:

- Querying data
- Broadcasting a transaction

## Connect to a Chain

To perform these actions, connect to the blockchain by using an `LCDClient` object, which represents a connection to a node running the light client daemon (LCD). The LCD serves as a RESTful API over HTTP. xpla.js abstracts away the details of making raw API calls and provide an interface with which you can work.

```ts
import { LCDClient } from "@c2xdev/xpla.js";

const xpla = new LCDClient({
  URL: "https://dimension-lcd.xpla.dev",
  chainID: "dimension-1",
});
```