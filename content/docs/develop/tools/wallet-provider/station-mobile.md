---
weight: 40
title: Station Mobile
---

# Station Mobile

Xpla Station Mobile is an application that enables users to interact with Xpla Core.

Xpla Station Mobile allows users to:

- Create wallets and send tokens
- Get involved with staking by browsing through validator information and delegating XPLA tokens.
- Use QRCodes for easy interactions when sending assets and recovering wallets

## URL Scheme

Xpla Station Mobile includes a custom [URL Scheme](https://developer.apple.com/documentation/xcode/defining-a-custom-url-scheme-for-your-app) that lets developers trigger different actions in the app.

These URL handlers can be opened by scanning a QR code or opening the link directly.

### Send

The send function allows a user to send a specified amount of funds to a recipient. This function can be used to accept payment for goods and other point-of-sale configurations.

#### URL

```
xplastation://send/?payload=${base64 json}
```

#### Payload Format

| Key     | Description                                   | Required? |
| ------- |-----------------------------------------------| --------- |
| address | Xpla address to send funds to                 |           |
| token   | Native token denom or cw20 contract address   | ✔️        |
| amount  | Amount of tokens in micro format              |           |
| memo    | Specific memo to include with the transaction |           |

#### Example

**Payload:**

```
{
  "address": "xpla1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8",
  "token": "axpla",
  "amount": "250000",
  "memo": "Order #1122"
}
```

**Base64 encoded payload:**

```
ewogICJhZGRyZXNzIjogInRlcnJhMWRjZWd5cmVrbHRzd3Z5eTB4eTY5eWRneG45eDh4MzJ6ZHRhcGQ4IiwKICAidG9rZW4iOiAidXVzZCIsCiAgImFtb3VudCI6ICIyNTAwMDAiLAogICJtZW1vIjogIk9yZGVyICMxMTIyIgp9
```

**Full URL with encoded payload:**

```
xplastation://send/?payload=ewogICJhZGRyZXNzIjogInRlcnJhMWRjZWd5cmVrbHRzd3Z5eTB4eTY5eWRneG45eDh4MzJ6ZHRhcGQ4IiwKICAidG9rZW4iOiAidXVzZCIsCiAgImFtb3VudCI6ICIyNTAwMDAiLAogICJtZW1vIjogIk9yZGVyICMxMTIyIgp9
```

**Full URL in QR code:**

TODO

**Find out more on [GitHub](https://github.com/c2xdev/station-mobile/#app-scheme).**
