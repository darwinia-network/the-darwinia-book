# bin

> [darwinia/bin/node][0]

## `darwinia/bin/node/cli`

Darwinia CLI library.

This package has two Cargo features:

- `cli` (default): exposes functions that parse command-line options, then start and run the
node as a CLI application.

- `browser`: exposes the content of the `browser` module, which consists of exported symbols
that are meant to be passed through the `wasm-bindgen` utility and called from JavaScript.
Despite its name the produced WASM can theoretically also be used from NodeJS, although this
hasn't been tested.


## `darwinia/bin/node/executor`

A `CodeExecutor` specialization which uses natively compiled runtime when the wasm to be executed is equivalent to the natively compiled code.

## `darwinia/bin/node/primitives`

Low-level types used throughout the Substrate code.

## `darwinia/bin/node/rpc-client`

Example darwinia RPC client code.

This module shows how you can write a Rust RPC client that connects to a running darwinia node and use staticly typed RPC wrappers.

## `darwinia/bin/node/rpc`

A collection of node-specific RPC methods.

Since `darwinia` core functionality makes no assumptions about the modules used inside the runtime, so do RPC methods defined in `sc-rpc` crate. It means that `client/rpc` can't have any methods that need some strong assumptions about the particular runtime.

The RPCs available in this crate however can make some assumptions about how the runtime is constructed and what `SRML` modules are part of it. Therefore all node-runtime-specific RPCs can be placed here or imported from corresponding `SRML` RPC definitions.

## `darwinia/bin/node/runtime`

The Darwinia runtime. This can be compiled with `#[no_std]`, ready for Wasm.


[0]: https://github.com/darwinia-network/darwinia/tree/develop/bin/node
