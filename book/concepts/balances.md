# Balances

`Darwinia Balances` usually mean `KTON` and `RING`, just like what we have already learned from the [introduction](../index.md): 

+ `Ring` is the native token for the Darwinia Network, it can be used as gas for transactions.

+ `Kton` is the other kind token in `darwnia` that can be awarded by locking `RING` for 3 - 36 months in the process of Staking.

`KTON` **can be pledged to receive Staking power, so as to participate in POS mining as well**. Users may Stake via pledging `KTON`. However, if the user takes back his or her staking `KTON`, then the related POS mining will be stopped, and it will take 14 days for the unpledged `KTON` to arrive.

## ImBalance

> Balances module simply reduces or increases its total issuance.

`Imbalances` can either be **Positive**(funds were added somewhere without being subtracted elsewhere - e.g. a reward) or **Negative**(funds deducted somewhere without an equal and opposite addition - e.g. a slash or system fee payment).

Since they are unsigned, the actual type is always `Positive` or `Negative`. The trait makes no distinction except to define the Opposite type.

New instances of zero value can be created (zero) and destroyed (drop_zero).

`Existing instances` can be split and merged either consuming self with merge or mutating self with subsume. If the target is an Option, then maybe *merge and maybe* subsume might work better. `Instances` can also be offset with an Opposite that is less than or equal to in value.

You can always retrieve the raw balance value using peek.
