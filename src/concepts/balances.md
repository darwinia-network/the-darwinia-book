# Balances

`Darwinia Balances` usually mean `KTON` and `RING`, like what we have already learned from the [introduction](../index.md): 

+ `Ring` is the native token for the Darwinia Network, it can be used as gas for transactions.

+ `Kton` is the other kind token in `darwnia` that can be awarded by locking `RING` for 3 - 36 months in the process of Staking.

`KTON` **can be pledged to receive Staking power, so as to participate in POS mining as well**. Users may Stake via pledging `KTON`. However, if the user takes back his or her staking `KTON`, then the related POS mining will be stopped, and it will take 14 days for the unpledged `KTON` to arrive.


## Burn
> TODO

## Weight
> TODO

## Terminology

- **Existential Deposit:** The minimum balance required to create or keep an account open. This prevents
"dust accounts" from filling storage. When the free plus the reserved balance (i.e. the total balance)
  fall below this, then the account is said to be dead; and it loses its functionality as well as any
  prior history and all information on it is removed from the chain's state.
  No account should ever have a total balance that is strictly between 0 and the existential
  deposit (exclusive). If this ever happens, it indicates either a bug in this module or an
  erroneous raw mutation of storage.

- **Total Issuance:** The total number of units in existence in a system.

- **Reaping an account:** The act of removing an account by resetting its nonce. Happens after its
total balance has become zero (or, strictly speaking, less than the Existential Deposit).

- **Free Balance:** The portion of a balance that is not reserved. The free balance is the only
  balance that matters for most operations.

- **Reserved Balance:** Reserved balance still belongs to the account holder, but is suspended.
  Reserved balance can still be slashed, but only after all the free balance has been slashed.

- **Imbalance:** A condition when some funds were credited or debited without equal and opposite accounting.

- **Lock:** A freeze on a specified amount of an account's free balance until a specified block number. Multiple
locks always operate over the same funds, so they "overlay" rather than "stack".

