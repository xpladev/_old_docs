---
weight: 60
title: Interacting with the Contract
---

# Interacting with the Contract

{{< hint info >}}
**Note**  
You can also follow these steps in the official web wallet for Xpla, [Xpla wallet](https://wallet.xpla.io).
{{< /hint >}}

## Requirements

You should also have the latest version of `xplad` by building the latest version of Xpla Core. You will configure `xplad` to use it against your isolated testnet environment.

In a separate terminal, make sure to set up the following mnemonic:

```sh
xplad keys add test1 --recover
```

Using the mnemonic:

```
satisfy adjust timber high purchase tuition stool faith fine install that you unaware feed domain license impose boss human eager hat rent enjoy dawn
```

## Uploading Code

Make sure that the **optimized build** of `my_first_contract.wasm` that you created in the last section is in your current working directory.

```sh
xplad tx wasm store artifacts/my_first_contract.wasm --from test1 --chain-id=tesseract-1 --gas=auto --fees=100000axpla --broadcast-mode=block
```
Or, if you are on an arm64 machine:

```sh
xplad tx wasm store artifacts/my_first_contract-aarch64.wasm --from test1 --chain-id=tesseract-1 --gas=auto --fees=100000axpla --broadcast-mode=block
```

You should see output similar to the following:

```sh
height: 6
txhash: 83BB9C6FDBA1D2291E068D5CF7DDF7E0BE459C6AF547EC82652C52507CED8A9F
codespace: ""
code: 0
data: ""
rawlog: '[{"msg_index":0,"log":"","events":[{"type":"message","attributes":[{"key":"action","value":"store_code"},{"key":"module","value":"wasm"}]},{"type":"store_code","attributes":[{"key":"sender","value":"xpla1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8"},{"key":"code_id","value":"1"}]}]}]'
logs:
- msgindex: 0
  log: ""
  events:
  - type: message
    attributes:
    - key: action
      value: store_code
    - key: module
      value: wasm
  - type: store_code
    attributes:
    - key: sender
      value: xpla1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8
    - key: code_id
      value: "1"
info: ""
gaswanted: 681907
gasused: 680262
tx: null
timestamp: ""
```

As you can see, your contract was successfully instantiated with Code ID #1.

You can check it out:

```sh
xplad query wasm code 1
codeid: 1
codehash: KVR4SWuieLxuZaStlvFoUY9YXlcLLMTHYVpkubdjHEI=
creator: xpla1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8
```

## Creating the Contract

You have now uploaded the code for your contract, but still don't have a contract. Create it with the following InitMsg:

```json
{
  "count": 0
}
```

You can compress the JSON into 1 line with [this online tool](https://goonlinetools.com/json-minifier/).

```sh
xplad tx wasm instantiate 1 '{"count":0}' --from test1 --chain-id=tesseract-1 --fees=10000axpla --gas=auto --broadcast-mode=block
```

You should get a response like the following:

```sh
height: 41
txhash: AEF6F2FA570029A5D4C0DA5ACFA4A2B614D5811E29EEE10FF59F821AFECCD399
codespace: ""
code: 0
data: ""
rawlog: '[{"msg_index":0,"log":"","events":[{"type":"instantiate_contract","attributes":[{"key":"owner","value":"xpla1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8"},{"key":"code_id","value":"1"},{"key":"contract_address","value":"xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5"}]},{"type":"message","attributes":[{"key":"action","value":"instantiate_contract"},{"key":"module","value":"wasm"}]}]}]'
logs:
- msgindex: 0
  log: ""
  events:
  - type: instantiate_contract
    attributes:
    - key: owner
      value: xpla1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8
    - key: code_id
      value: "1"
    - key: contract_address
      value: xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5
  - type: message
    attributes:
    - key: action
      value: instantiate_contract
    - key: module
      value: wasm
info: ""
gaswanted: 120751
gasused: 120170
tx: null
timestamp: ""
```

From the output, you can see that your contract was created above at: `xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5`. Take note of this contract address, as you will need it for the next section.

Check out your contract information:

```sh
xplad query wasm contract xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5
address: xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5
owner: xpla1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8
codeid: 1
initmsg: eyJjb3VudCI6MH0=
migratable: false
```

You can use the following to decode the Base64 InitMsg:

```sh
echo eyJjb3VudCI6MH0= | base64 --decode
```

This will produce the message you used when initializing the contract:

```json
{ "count": 0 }
```

## Executing the Contract

Let's do the following:

1. Reset count to 5
2. Increment twice

If done properly, you should get a count of 7.

#### Reset

First, to burn:

```json
{
  "reset": {
    "count": 5
  }
}
```

```sh
xplad tx wasm execute xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5 '{"reset":{"count":5}}' --from test1 --chain-id=tesseract-1 --fees=1000000axpla --gas=auto --broadcast-mode=block
```

#### Incrementing

```json
{
  "increment": {}
}
```

```sh
xplad tx wasm execute xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5 '{"increment":{}}' --from test1 --chain-id=tesseract-1 --gas=auto --fees=1000000axpla --broadcast-mode=block
```

#### Querying count

Check the result of your executions!

```json
{
  "get_count": {}
}
```

```sh
xplad query wasm contract-store xpla18vd8fpwxzck93qlwghaj6arh4p7c5n896xzem5 '{"get_count":{}}'
```

Expected output:

```
query_result:
  count: 7
```

Excellent! Congratulations, you've created your first smart contract, and now know how to get developing with the Xpla dApp Platform.

## What's Next?

So far you've walked through a simple example of a smart contract, that modifies a simple balance within its internal state. Although this is enough to make a simple dApp, you can power more interesting applications by **emitting messages**, which will enable you to interact with other contracts as well as the rest of the blockchain's module.

Check out a couple more examples of smart contracts using Xpla's smart contract [repo](https://github.com/xpladev/cosmwasm-contracts).
