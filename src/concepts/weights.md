# Weights

A number of resources in darwinia can be limited, such as storage or computation. Weights exist to prevent individual components of the chain from consuming too much of any resource.

## Fee

Consuming some weights should generally incur a [fee](./fee.md). 

## Block Weight and Length Limit

Aside from affecting fees, the main purpose of the weight system is to **prevent a block from being filled with too many transactions**. While processing transactions within a block, the System pallet accumulates both the total length of the block (sum of encoded transactions in bytes) and the total weight of the block. 


## Weights in darwinia

| pallet             | function                  | weight    |
|--------------------|---------------------------|-----------|
| balances           | force\_transfer           | 1,000,000 |
| balances           | set\_balance              | 1,000,000 |
| balances           | transfer                  | 1,000,000 |
| balances           | transfer\_keep\_alive     | 1,000,000 |
| -                  |                           |           |
| elections-phragmen | remove\_member            | 2,000,000 |
| elections-phragmen | renounce\_candidacy       | 2,000,000 |
| elections-phragmen | report\_defunct\_voter    | 1,000,000 |
| elections-phragmen | summit\_candidacy         | 500,000   |
| elections-phragmen | vote                      | 100,000   |
| elections-phragmen | remove\_voter             | 10,000    |
| -                  |                           |           |
| staking            | cancel\_deferred\_slashed | 1,000,000 |
| staking            | nominate                  | 750,000   |
| staking            | set\_controller           | 750,000   |
| staking            | validate                  | 750,000   |
| staking            | bond                      | 500,000   |
| staking            | bond\_extra               | 500,000   |
| staking            | chill                     | 500,000   |
| staking            | set\_payee                | 500,000   |
| staking            | unbond                    | 400,000   |
| staking            | force\_unstake            | 10,000    |
| staking            | set\_invulnerables        | 10,000    |
| staking            | force\_new\_era           | 5,000     |
| staking            | force\_new\_era\_always   | 5,000     |
| staking            | force\_no\_eras           | 5,000     |
| staking            | set\_validator\_count     | 5,000     |
| -                  |                           |           |
| treasury           | propose\_spend            | 500,000   |
| treasury           | tip\_new                  | 150,000   |
| treasury           | approve\_proposal         | 100,000   |
| treasury           | reject\_proposal          | 100,000   |
| treasury           | report\_awesome           | 100,000   |
| treasury           | close\_tip                | 50,000    |
| treasury           | retract\_tip              | 50,000    |
| treasury           | tip                       | 50,000    |

