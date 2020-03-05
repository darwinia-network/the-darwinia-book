# Introduction

This [book][0] is about [Darwinia][1], as an open application cross-chain protocol based on [Substrate][2], `Darwinia` focuses on the construction of future Internet of Tokens, including the cross-chain of game tokens, NFT, Stablecoins, and Appchain.

## Background

The world is being blockchainized and tokenized. Fungible tokens, which has been generally used in the financial industry, together with Non-fungible tokens, which are becoming more and more recognized in the game industry, will greatly enhance the openness and collaboration of finance and game sector.

These tokens are being connected and merged, and the ways of such connection and merger are trends to diversified as well. Such connections might be performed with smart contracts, Dapp, or appchain protocols, that lead to the formation of an open token-network. Darwinia Network powered by polkadot app-parachain technology, via develop infrastructure and core-applications, to support the growth of the token-network. Darwinia focuses its major application in games and de-fi sector.


## Architecture Design

In the process of using `blockchain` technology to create new `DAPP`, we found several problems for the mass promotion and utilization of `blockchain` technology:

1. The current blockchain infrastructure is not yet able to meet the requirements of user experience.
2. Traditional game vendors lack blockchain experience.
3. Blockchain games are split among different public chains.

However, `blockchain games` or Dapps can easily perform `cross-chain` interactions for game inventories and game operations through the `Darwinia Network`. For example, `Cryptokitties` can transform its NFT (Kitties) on the `Ethereum` into NFT on `EOS` through the `Darwinia chain`; players on the `Ethereum` and players on the `EOS` can play `Evolution Land` game simultaneously through the `Darwinia Network`. **At the same time, thanks to the Polkadot ecosystem, Darwinia Network can link to a wider range of games and players.**

The architecture relationship of Darwinia Relay Chain, Darwinia AppChain, Polkadot Relay Chain, etc. is shown as below. 

![Darwinia architecture][3]


## Darwinia Relay Chain

**Darwinia Relay Chain is the most important part of the Darwinia Network**, it is also the hub of each App- Parachain, to this end, we divided the operating mode of Darwinia relay chain into `Solo mode` and `Polkadot connection mode`.

### Solo Mode

Darwinia Network can choose to operate as an independent public-chain network and is responsible for its own consensus security, with its core business and application services, including the cross-chain functionality of each application chain, controlled by Darwinia Network itself.

### Polkadot Connection Mode

In Polkadot connection mode, in addition to operating as a relay chain for Darwinia Network, it also serves as a Parachain for Polkadot.

## Economic Model

### RING

The native token for the Darwinia Network is `RING`, `RING` can be used as gas for transactions. Gas include transaction fees, contract execution fees, network bandwidth charges, storage fees, and more.

![Benefits][4]

### KTON

To encourage users to make long term commitments and pledge, users can choose to **lock `RING` for 3 - 36 months** in the process of Staking, and the system will offer a `KTON` token as reward for users participating in Staking. During the committed pledge period, users cannot unlock their RING. (Unless they utilise triple the amount of KTON as penalty).

## Community Ecosystem

### Protocol Researcher

The protocol and standard research’s work is divided into **two parts**. **The first part** comes from the community. `Darwinia Network` accepts any `RFC` submission from the community, including new additions, improvements and modifications. These `RFCs` will be open to the community for full discussion and research to reach a consensus. **The second part** is from the `core research team`, which is responsible for organizing `RFCs`, organizing `RFC` peer audits and security audits, using `Darwinia Network` governance models and tools for protocol governance and voting, and forming a final agreement design draft for delivery to the protocol development team.

### Developer

Develop and improve `Darwinia Network`, `Darwinia AppChain` and `related services`, and develop applications and services using the `Darwinia Network` and the `Darwinia AppChain`. Early community open source software development, especially important infrastructure software development (including network protocol design, protocol implementation, node software, wallet, browser, etc.), will be sponsored and supported by the Darwinia Network oundation, currently the main `Darwinia Network` open source software developer is [Itering Tech][5].


### Dapp Developer

`Dapp developers` include developers who develop applications based on the `Darwinia Web Smart Contracts module`, as well as developers who develop Dapp on the public chain, such as blockchain games or Defi applications on platforms such as `Ethereum`, `TRON` or `EOS`. For the Dapp and game inventories on the public chain, bridge parachain of Darwinia Network can be connected to the Darwinia Network for `cross-chain` transfer operations.

### AppChain Developer

`Application chain developers` developing with the `Darwinia Web Application` Suite (Darwinia AppChain).

[0]: https://darwinia-network.github.io/the-darwinia-book
[1]: https://github.com/darwinia-network/darwinia
[2]: https://github.com/paritytech/substrate
[3]: https://github.com/darwinia-network/rfcs/raw/master/RFC/zh_CN/images/0007-darwinia-architecture.jpeg
[4]: https://github.com/darwinia-network/rfcs/raw/master/RFC/zh_CN/images/reward.jpeg
[5]: https://itering.io
