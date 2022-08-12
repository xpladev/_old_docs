---
weight: 120
title: Wallet
---

# Wallet

This guide is for advanced features of the Xpla Vault. If this is your first time using Xpla Vault, follow the [Xpla Vault tutorial]({{< ref "xpla-vault" >}}).

For information on using multisig wallets in Xpla Vault, see [Multisig wallets]({{< ref "multisig-wallets" >}})

## Create a wallet

1. Open the Xpla web wallet and click **New wallet**.

1. Type in a secure wallet name and password.

1. Confirm your password.

1. Using a pen and paper, write down your 24-word seed phrase exactly as it appears. Number each word to make verifying easier.

   {{< hint danger >}}
   **Danger**  
   Anyone with your seed phrase can access your money, and there is no recourse for someone stealing your seed phrase. To protect your seed phrase, consider the following tips:
   - Never save or store your seed phrase as a digital file on any device.
   - Always write down your seed phrase with a pen and paper.
   - Store the paper with your seed phrase on it somewhere safe.
   - Never give your seed phrase to anyone, not even support staff.
   {{< /hint >}}

1. Verify your writing to make sure every word is spelled correctly and in the right order. If you numbered your phrase, it can be helpful to verify it backward.

1. Check the box ensuring you wrote down your seed phrase, and click **Next**.

1. Confirm your seed phrase by typing or selecting the correct words in each prompt.

1. Click **Create a wallet**.

Congratulations! You have just created a Xpla Vault.

## Select a Wallet

Follow these steps to connect to a wallet previously accessed on your device.

1. Open Xpla Vault and click **Connect**.

1. Click **Select wallet** and select the wallet you want to connect to.

1. Enter the password of the wallet and click **Next**.

Xpla Vault is now connected to your selected wallet. To change wallets, [disconnect your wallet](#disconnect-a-wallet) and follow these steps again.

## Connect to a Wallet Using a Private Key

Use a private key to access your wallet from other devices. Unlike recovering your wallet using a seed phrase, private keys allow you to keep your wallet name and password. Follow these steps to connect to an existing wallet using a private key. You will need access to your existing wallet.

### Export Your Private Key

1. Open Xpla Vault and connect to your wallet.

1. Locate your wallet address on Xpla Vault. Click the gear icon next to your wallet address.

1. Click **Export private key**.

1. Enter your password and click **Generate key**.

You can now access your private key. Do not share your private key with anyone. Anyone with your private key and password can access your account.

### Import Your Private Key

1. Open Xpla Vault and click **Connect**.

1. Click **Import private key**.

1. Enter your private key and password.

1. Click **Submit**.

Your private key has been imported to the device you are using. You can now use your wallet name and password to access your wallet on your device. Repeat this process for any device you wish to access your wallet.

## Connect to a Wallet Using a QR Code

Use a QR code to access your wallet on a mobile device. Unlike recovering your wallet using a seed phrase, QR codes allow you to keep your wallet name and password. Follow these steps to connect to an existing wallet using a private key QR code. You will need access to your existing wallet.

### Export Your QR Code Using Desktop

1. Open Xpla Vault and connect to your wallet.

1. Locate your wallet address on Xpla Vault. Click the gear icon next to your wallet address.

1. Click **Export with QR code**.

1. Enter your password and click **Generate QR code**.

### Export Your QR Code Using the Mobile App

1. Open the Xpla Vault app and connect to your wallet.

1. Tap the gear icon in the upper right corner of the app.

1. Click **Export wallet with QR code**.

1. Enter your password.

You can now access your private key QR code. Do not share your private key with anyone. Anyone with your private key and password can access your account.

### Import Your QR Code

1. Open the Xpla Vault and tap **Recover wallet**.

1. Tap **Scan QR code**.

1. Scan your QR code using your device's camera and enter your password.

1. Tap **Next**.

Your private key has been imported to the device you are using. You can now use your wallet name and password to access your wallet on your device. Repeat this process for any device you wish to access your wallet.

## Recover a Wallet Using a Seed Phrase

If you forgot or deleted your login info, you can recover a wallet using your seed phrase. You can also use this method to change your wallet name.

1. Open Xpla Vault and click **Connect**.

1. Click **Recover existing wallet**.

1. Enter a wallet name and password. Confirm your password.

1. Enter your seed phrase and click **Next**.

You can now access your wallet with your login and password.

## Disconnect a Wallet

1. Locate your wallet address on Xpla Vault. Click the gear icon next to your wallet address.

1. Select **disconnect** from the options.

Your wallet is now disconnected.

## Delete a Wallet

Deleting a wallet deletes the wallet name, password, and private key from your device. You can access the wallet again by entering your [seed phrase](#recover-a-wallet-using-a-seed-phrase) or [private key and password](#connect-to-a-wallet-using-a-private-key). Deleting a wallet from one device does not delete it from other devices.

{{< hint danger >}}
**Write down your seed phrase**  
Before you delete your wallet, always make sure you have your seed phrase and private key. Never store your seed phrase on a digital device. Without a seed phrase or private key and password, your wallet and funds will be permanently inaccessible. Always store your seed phrase in a secure location.
{{< /hint >}}

1. Open Xpla Vault and connect to your wallet.

1. Locate your wallet address on Xpla Vault. Click the gear icon next to your wallet address.

1. Select **Delete wallet**.

1. Follow the prompt and click **Delete**.

Your wallet is now deleted. You can only access it again by entering your [seed phrase](#recover-a-wallet-using-a-seed-phrase) or [private key and password](#connect-to-a-wallet-using-a-private-key).

## Change Your Password

Follow these steps to change your password. Changing your password only changes your wallet password on a single device. Repeat these steps to change your wallet password on other devices.

1. Open Xpla Vault and connect to your wallet.

1. Locate your wallet address on Xpla Vault. Click the gear icon next to your wallet address.

1. Select **Change password** from the options.

1. Enter your current password and your new password. Confirm your new password.

1. Click **Change password**.

Your wallet password is now changed on your device. Repeat these steps to change your wallet password on other devices.
