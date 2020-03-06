# Staking

## Terminology

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


## Scenarios

### Staking

Almost any interaction with the Staking module requires a process of _**bonding**_ (also known as being a _staker_). To become *bonded*, a fund-holding account known as the _stash account_, which holds some or all of the funds that become frozen in place as part of the staking process, is paired with an active **controller** account, which issues instructions on how they shall be used.

There are three possible roles that any staked account pair can be in: `Validator`, `Nominator` and `Idle` (defined in `StakerStatus`). There are three corresponding instructions to change between roles, namely: `validate`, `nominate`, and `chill`.

### Validating

A **validator** takes the role of either validating blocks or ensuring their finality, maintaining the veracity of the network. A validator should avoid both any sort of malicious misbehavior and going offline. Bonded accounts that state interest in being a validator do NOT get immediately chosen as a validator. Instead, they are declared as a _candidate_ and they _might_ get elected at the _next era_ as a validator. The result of the election is determined by nominators and their votes.


### Nomination

A **nominator** does not take any _direct_ role in maintaining the network, instead, it votes on a set of validators  to be elected. Once interest in nomination is stated by an account, it takes effect at the next election round. The funds in the nominator's stash account indicate the _weight_ of its vote. Both the rewards and any punishment that a validator earns are shared between the validator and its nominators. This rule incentivizes the nominators to NOT vote for the misbehaving/offline validators as much as possible, simply because the nominators will also lose funds if they vote poorly.


### Rewards and Slash

The **reward and slashing** procedure is the core of the Staking module, attempting to _embrace valid behavior_ while _punishing any misbehavior or lack of availability_.

Slashing can occur at any point in time, once misbehavior is reported. Once slashing is determined, a value is deducted from the balance of the validator and all the nominators who voted for this validator (values are deducted from the _stash_ account of the slashed entity).

Slashing logic is further described in the documentation of the `slashing` module.

Similar to slashing, rewards are also shared among a validator and its associated nominators. Yet, the reward funds are not always transferred to the stash account and can be configured. See [Reward Calculation](#reward-calculation) for more details.

### Chilling

Finally, any of the roles above can choose to step back temporarily and just chill for a while. This means that if they are a nominator, they will not be considered as voters anymore and if they are validators, they will no longer be a candidate for the next election.

