# DJ

[![dj](https://github.com/darwinia-network/dj/workflows/nodejs/badge.svg)](https://github.com/darwinia-network/dj)
[![dj](https://img.shields.io/npm/v/@darwinia/dj)](https://www.npmjs.com/package/@darwinia/dj)
[![LICENSE](https://img.shields.io/crates/l/darwinia-shadow.svg)](https://choosealicense.com/licenses/gpl-3.0/)

DJ is the relayer tool of Darwinia, it contains several listeners to handle the
relay process.

## How to test?

### Easy version

```shell
$ npm i -g @darwinia/dj
$ dj -v
```

Run the commands above and we'll start testing the relay bridge.

### Hack version

```shell
$ git clone https://github.com/darwinia-network/dj.git
$ cd dj && yarn && ts-node index.ts
```


## Listeners

### 1. Ethereum Transaction Listener

The first listener of DJ is the `Ethereum transaction listener`, which will listen the Ethereum and discover transactions interacting with Darwinia contract.


### 2. Relay Listener

The `relay listener` triggers every a fixed time range, if DJ has discovered transactions, it'll batch and send all of them to Darwinia for verifying.

As the transactions are verified, the relay process is almost done.

### 3. Guard Listener

The part is a protection system for checking the relayed data, if you run `DJ` with `council` account or `sudo` account, the `guard Listener` will trigger.
