# Shadow

[![rust](https://github.com/darwinia-network/shadow/workflows/shadow/badge.svg)](https://github.com/darwinia-network/shadow)
[![crate](https://img.shields.io/crates/v/darwinia-shadow.svg)](https://crates.io/crates/darwinia_shadow)
[![doc](https://img.shields.io/badge/current-docs-brightgreen.svg)](https://docs.rs/darwinia_shadow/)
[![LICENSE](https://img.shields.io/crates/l/darwinia-shadow.svg)](https://choosealicense.com/licenses/gpl-3.0/)

The shadow service for relayers and verify workers to retrieve header data and generate proof. Shadow will index the data it needs from blockchain nodes, such as Ethereum and Darwinia.

## How to test?

### Easy version

Just use the open shadow service at:

+ [https://shadow.darwinia.network](https://shadow.darwinia.network)
+ [https://testnet.shadow.darwinia.network](https://testnet.shadow.darwinia.network)

### Hack version

```shell
$ git clone https://github.com/darwinia-network/shadow.git
$ cd shadow && cargo run -- run -v
```

## Proofs

Shadow service generates proofs for relay system, `Ethash Proof`, `MMR Proof` and `Receipt Proof`.

### Ethash Proof

The meaning of Ethash Proof is to verify the Ethereum block which is relaying to Darwinia is **the Ethereum Block**.

### MMR Proof

MMR Proof describes the relationship betweeen the confirmed Ethereum block and the relaying Ethereum block, we have to pass this check.

### Receipt Proof

THe Receipt Proof is for the Ethereum Transactions, for checking they are what they are, yep, transactions should be Ethereum transcations interacting with Darwinia Ethereum contract.
