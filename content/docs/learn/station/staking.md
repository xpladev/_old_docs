---
weight: 100
title: Staking
---

# Manage staking <img src="/img/Staking.svg" height="40px">

Use this guide to manage your staking delegations in Station. To learn how to stake or withdraw rewards, visit the Station [desktop](download/station-desktop.md) or [mobile](download/station-mobile.md) tutorials.  

If this is your first time using Station, follow the [Station tutorial](download/station-desktop.md).

## Stake Xpla

Stake your Xpla to a validator to start earning rewards. Before you stake, make sure you have Xpla in your wallet. You can transfer Xpla from an [exchange](wallet.md).

1. Open Station and click **Staking**.

2. Select a Validator and click on their name in the **Moniker** column of the validator list.

3. In the **My delegations** section, click **Delegate**. A new window will appear.

4. In the **Amount** field, specify the amount of Xpla you want to delegate, and click **Next**.

   :::{admonition} Keep coins for fees
   :class: warning
   Always keep some coins to pay fees with. Never stake your entire wallet amount. Without money for fees, you can't make any transactions.
   :::

5. Double check the amounts and fees. Enter your password and click **Delegate**.

Congratulations, you've just delegated Xpla!

## Withdraw staking rewards

Rewards start accruing the moment you stake Xpla. Monitor your rewards in the staking section of Station. Once you have sufficient rewards, follow these steps to withdraw them:

1. Open Station and click **Staking**.

2. To claim all rewards, click **Withdraw all rewards** in the upper right corner of the staking page. To withdraw rewards only from a single validator, click on their name in the list and click **withdraw** on their page.  A new window will appear.

3. Review the amounts and specify which coin you want to pay fees in.

4. Enter your password and click **withdraw**.

Congratulations, you've just withdrawn your staking rewards!

## Redelegate

Redelegating lets you transfer staked Xpla from one validator to another without waiting the 21-day unstaking period. Redelegating happens instantly.

:::{warning}
When a user redelegates staked Xpla from one validator to another, the validator receiving the staked Xpla is barred from making further redelegation transactions for 21 days. This requirement only applies to the wallet that made the redelegation transaction.
:::

1. Open Station and connect your wallet. Click **Staking**.

2. Click on the validator you want to redelegate to.

3. Under the **My delegations** section, click **Redelegate**.

4. Select the validator you would like to redelegate from.

5. Enter the amount of Xpla you want to redelegate.

6. Confirm the amounts. Enter your password and click **Redelegate**.

Your staked Xpla will be transferred to the new validator.

## Undelegate

Undelegate Xpla to unstake it from a validator. The unstaking period takes 21 days to complete.

:::{warning}
Once started, the delegating or undelegating processes can't be stopped.
Undelegating takes 21 days to complete. The only way to undo a delegating or undelegating transaction is to wait for the unbonding process to pass. Alternatively, you can redelegate staked Xpla to a different validator without waiting 21 days.
:::

1. Open Station and connect your wallet. Click **Staking**.

2. Click on the validator you want to unstake from.

3. Click **Undelegate** under the **My delegations** section.

4. Enter the amount of Xpla you want to undelegate. Click **Next**.

4. Confirm the amounts. Enter your password and click **Undelegate**.

Your staked Xpla is unbonding. Please check back in 21 days to complete the process.
