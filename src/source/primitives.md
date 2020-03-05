# primitives

> [darwinia/primitives][0]

## `darwinia/primitives/ethash`

Apache-2 licensed Ethash implementation.

## `darwinia/primitives/merkle-patricia-trie`

Merkle patricia trie

## `darwinia/primitives/phragmen`

Rust implementation of the Phragmén election algorithm. This is used in several SRML modules to
optimally distribute the weight of a set of voters among an elected set of candidates. In the
context of staking this is mapped to validators and nominators.

The algorithm has two phases:
  - Sequential phragmen: performed in [`elect`] function which is first pass of the distribution
    The results are not optimal but the execution time is less.
  - Equalize post-processing: tries to further distribute the weight fairly among candidates.
    Incurs more execution time.

The main objective of the assignments done by phragmen is to maximize the minimum backed
candidate in the elected set.

+ Reference [implementation][4]
+ Further [details][5]


## `darwinia/primitives/sp-eth-primitives`

Ethereum primitives

[0]: https://github.com/darwinia-network/darwinia/tree/develop/primitives
