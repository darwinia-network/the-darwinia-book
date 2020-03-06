# Relay Chain

As we know, a blockchain is a chain of blocks, or we call them decentralized ledgers, famous projects like Bitcoin and Ethereum both are members of blockchains.

## Polkadot

`Darwinia` is a `Relay Chain` of `Polkadot`, so the first question is, what is `Polkadot`?

We can reach the explanation from its [official website][0]:

> `Polkadot` is a network protocol that allows arbitrary data—not just tokens—to be transferred across blockchains.
> 
> This means `Polkadot` is a true **multi-chain application environment** where things like `cross-chain` registries and `cross-chain` computation are possible.


## Relay Chain

`Polkadot`'s network structure contains `Parachains`, `Relay Chain` and `Bridges Chains`:

### Parachains

> application-specific blockchains

`Parachains` are the parallelizable blockchains (“para-chains”) that comprise the Polkadot network. Each parachain can have a unique architecture that best suits its application. Parachains are also used to parallelize transactions and achieve scalability. Parachains are connected and secured by the relay chain.

### Relay chain

> connects and validates parachains

The `relay chain` connects the components of the Polkadot network. It provides security to parachains and relays messages between them, as well as bridge chains. The messages can be transactions or any arbitrary data.

### Bridges chains

> connect Polkadot to external blockchains

`Bridges` are special parachains that allow communication to independent blockchains that are not secured by Polkadot's relay chain and instead use their own security, like Bitcoin or Ethereum.


## Darwinia

`Darwinia` is a `relay chain` of `Polkadot` in some way, actually, what `Polkadot` and its `relay chain` can do, is what `Darwinia` supports!


[0]: https://polkadot.network
