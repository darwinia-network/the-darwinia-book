# Source Code Trip

```sh
$ tree darwinia -I '|src|target|LICENSE|*.*|'
.
├── bin
│   └── node
│       ├── cli
│       │   ├── bin
│       │   └── res
│       ├── executor
│       ├── primitives
│       ├── rpc
│       ├── rpc-client
│       └── runtime
├── client
│   └── cli
├── frame
│   ├── balances
│   │   ├── kton
│   │   └── ring
│   ├── chainrelay
│   │   └── eth
│   │       ├── backing
│   │       └── relay
│   ├── elections-phragmen
│   ├── staking
│   ├── support
│   └── treasury
└── primitives
    ├── ethash
    ├── merkle-patricia-trie
    │   └── benches
    ├── phragmen
    └── sp-eth-primitives
```

- [bin](./bin.md)
- [client](./client.md)
- [frame](./frame/README.md)
  - [balances](./frame/balances.md)
  - [chainrelay](./frame/chainrelay.md)
  - [elections-phragmen](./frame/elections_phragmen.md)
  - [staking](./frame/staking.md)
  - [support](./frame/support.md)
  - [treasury](./frame/treasury.md)
- [primitives](./primitives.md)
