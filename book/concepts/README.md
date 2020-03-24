# Concepts

Gather all Terminologies.

```text
                                                                               +--------------+                 +-----+
                                                                   +-----+     | browser-demo |    +-----+      | src |
                                                                   | bin |   * +--------------+    | res |    * +-----+   +-------+
                                                                 * +-----+  *                      +-----+   *            | tests |
                                                               *           *                     *          *           * +-------+
                                                      +-----+ *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  
                                                      | cli |
                                                      +-----+                   +-----+                    +---------+
                                                     *       +----------+       | rpc |    +---------+     | testing |
                                                   *         | executor |     * +-----+    | runtime |   * +---------+
                                                 *         * +----------+    *           * +---------+  * 
                                               *          *                 *           *              *
                                  +----------+  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
                                  | bin/node |
                                  +----------+                  +------+
                                 *                              | ring |      +------+
                               *                              * +------+      | kton |
                             *                               *              * +------+     +-------+ 
                           *                   +----------+ *  *  *  *  *  *               | relay |      +--------+
                         *                     | balances |                              * +-------+      | baking |
                       *                     * +----------+                            *                * +--------+        +----------+
                     *                     *                   +----------------+ *  *  *  *  *  *  *  *                    | treasury |
                   *                     *                     | chainrelay/eth |                                         * +----------+
                 *                     *                       +----------------+                                        *
               *                     *                       *                                                          *
             *           +-------+ *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  * 
+----------+             | frame |     *              *                          *                 *                 *              *
| darwinia |  *  *  *  * +-------+      * +--------+   *                          * +------------+  *                 * +---------+  *
+----------+                              | claims |    * +--------------------+    | header-mmr |   * +---------+      | support |   * +---------+
             *                            +--------+      | elections-phragmen |    +------------+     | staking |      +---------+     | vesting |
               *                                          +--------------------+                       +---------+                      +---------+
                 * 
                   *
                     * +-----------+
                       | primtives |
                       +-----------+ *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *  *
                                         *                       *                 *                             *
                                          * +----------------+    *                 * +----------------------+    *
                                            | eth-primitives |     * +--------+       | merkle-patricia-trie |     * +----------+
                                            +----------------+       | ethash |       +----------------------+       | phtagmen |
                                                                     +--------+                                      +----------+
```

## Balances

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


## Staking

- **Staking**: The process of locking up funds for some time, placing them at risk of slashing
(loss) in order to become a rewarded maintainer of the network.
- **Validating**: The process of running a node to actively maintain the network, either by
producing blocks or guaranteeing finality of the chain.
- **Nominating**: The process of placing staked funds behind one or more validators in order to
share in any reward, and punishment, they take.
- **Stash account**: The account holding an owner's funds used for staking.
- **Controller account**: The account that controls an owner's funds for staking.
- **Era**: A (whole) number of sessions, which is the period that the validator set (and each
validator's active nominator set) is recalculated and where rewards are paid out.
- **Slash**: The punishment of a staker by reducing its funds.

## Treasury

- **Proposal:** A suggestion to allocate funds from the pot to a beneficiary.
- **Beneficiary:** An account who will receive the funds from a proposal iff
the proposal is approved.
- **Deposit:** Funds that a proposer must lock when making a proposal. The
deposit will be returned or slashed if the proposal is approved or rejected
respectively.
- **Pot:** Unspent funds accumulated by the treasury module.
