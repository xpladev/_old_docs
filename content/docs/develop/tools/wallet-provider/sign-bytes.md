---
weight: 20
title: Sign Bytes
---

# Signing Bytes

You can sign arbitrary bytes with [Wallet Provider](https://www.npmjs.com/package/@xpla/wallet-provider) in a React-based web application. This action is useful for verifying account ownership without having to post a transaction to the chain, and is commonly used as a form of simple user authentication.

{{< hint info >}}
**Tip**  
Not using React? Use the [wallet-controller](https://www.npmjs.com/package/@xpla/wallet-controller) instead.
{{< /hint >}}

The Wallet Provider comes with a `useConnectedWallet` hook, which lets you trigger actions from a XPLA Vault that's connected to the web page. The `connectedWallet` object includes a `.signBytes()` method, which prompts the user to sign the data and then returns an object of type `SignBytesResult`. The returned `SignBytesResult` object contains the address of the signer and the signed data.

The `verifyBytes` function then compares the original `TEST_BYTES` against the signature and public key pairing returned by the `SignBytesResult`. If `verifyBytes` returns `true`, then the account is owned by the connected wallet. Likewise, if `verifyBytes` returns `false`, then the account is not owned by the connected wallet. In this way, the owner of the associated wallet is verified without having to produce an on-chain action or pay gas fees.

{{< hint info >}}
**Tip**  
You can see how the `verifyBytes` function works [here](https://github.com/xpladev/wallet-provider/blob/4e601c2dece7bec92c9ce95991d2314220a2c954/packages/src/%40xpladev/wallet-controller/verifyBytes.ts#L1).
{{< /hint >}}

Wallet Provider also supplies useful error types that can be used with a `catch` statement notify the user whether the signing was successful:

```ts
 import {
  SignBytesFailed,
  SignBytesResult,
  Timeout,
  useConnectedWallet,
  UserDenied,
  verifyBytes,
} from '@xpla/wallet-provider';
import React, { useCallback, useState } from 'react';

const TEST_BYTES = Buffer.from('hello'); // resolves to <Buffer 68 65 6c 6c 6f>

export function SignBytesSample() {
  const [txResult, setTxResult] = useState<SignBytesResult | null>(null);
  const [txError, setTxError] = useState<string | null>(null);
  const [verifyResult, setVerifyResult] = useState<string | null>(null);

  const connectedWallet = useConnectedWallet();

  const signBytes = useCallback(async () => {
    if (!connectedWallet) {
      return;
    }

    try {
        const signedBytes: SignBytesResult = await connectedWallet.signBytes(TEST_BYTES);
        setTxResult(signedBytes);
        setTxError(null);
        const result = verifyBytes(TEST_BYTES, signedBytes.result);
        setVerifyResult(result ? 'Verified' : 'Verification failed');

    } catch (error) {
        setTxResult(null);
        setVerifyResult(null);
        if (error instanceof UserDenied) {
            setTxError('User Denied');
        } else if (error instanceof Timeout) {
            setTxError('Timeout');
        } else if (error instanceof SignBytesFailed) {
            setTxError('Sign Bytes Failed');
        } else {
            setTxError(
            'Unknown Error: ' +
                (error instanceof Error ? error.message : String(error)),
            );
        }
    }
  }, [connectedWallet]);

  return (
    <div>
      <h1>Sign Bytes Sample</h1>

      {connectedWallet?.availableSignBytes &&
        !txResult &&
        !txError &&
        !verifyResult && (
          <button onClick={() => signBytes()}>
            Sign bytes with {connectedWallet.walletAddress}
          </button>
        )}

      {txResult && <pre>{JSON.stringify(txResult, null, 2)}</pre>}

      {txError && <pre>{txError}</pre>}

      {verifyResult && <pre>{verifyResult}</pre>}

      {!connectedWallet && <p>Wallet not connected!</p>}

      {connectedWallet && !connectedWallet.availableSignBytes && (
        <p>This connection does not support signBytes()</p>
      )}
    </div>
  );
}
```
You can find this code used in context in [GitHub](https://github.com/xpladev/wallet-provider/blob/main/templates/create-react-app/src/components/SignBytesSample.tsx).
