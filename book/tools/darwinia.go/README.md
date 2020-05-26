# darwinia.go

[![Golang CI][workflow-badge]][github]

## Installation

Just supports OSX now

```
# Tap darwinia homebrew
brew tap darwinia-network/darwinia

# Install
brew install dargo
```

## Contribute and Build

```
# Clone darwinia.go
git clone https://github.com/darwinia-network/darwinia.go.git

# Make the binary
cd darwinia.go/dargo && make

# Check the version
./target/dargo version
```

## Usage

```sh
$ dargo
The way to Go

Usage:
  dargo [command]

Available Commands:
  epoch       Calculate epoch cache
  header      Get eth block by number
  help        Help about any command
  proof       Proof the block by number
  shadow      Start shadow service
  version     Print the version number of dargo

Flags:
  -h, --help   help for dargo

Use "dargo [command] --help" for more information about a command.

```

## Shadow RPC examples

Exports your `INFURA_KEY` to envrioment

```
export INFURA_KEY='<your-infura-key>'
```

Starts shadow service:

```
# Start shadow service at port 3000
dargo shadow 3000
```

Avaiable enviroment variables:

| Key              | Description                                                    | default |
|------------------|----------------------------------------------------------------|---------|
| `INFURA_KEY`     | infura key, doesn't know what's [infura][infura]?              | `""`    |
| `SHADOW_GENESIS` | shadow service will block all requests before `SHADOW_GENESIS` | `0`     |

The shadow service of dargo follows the [spec][spec].

### Shadow.GetEthHeaderByNumber

```
curl -d '{"method":"shadow_getEthHeaderByNumber","params":{"number": 0}}' http://127.0.0.1:3000
```

### Shadow.GetEthHeaderByHash

```
curl -d '{"method":"shadow_getEthHeaderByHash","params":{"hash": "0x8d0dd9b1f5854bbdc60d06aa04e6e953000aa53f6c6486f18f08666bc17ea228"}}' http://127.0.0.1:3000
```

### Shadow.GetEthHeaderWithProofByNumber

```
curl -d '{"method":"shadow_getEthHeaderWithProofByNumber","params":{"block_num": 1, "transcation": false, "options": {"format": "json"}}}' http://127.0.0.1:3000
```

### Shadow.GetEthHeaderWithProofByHash

```
curl -d '{"method":"shadow_getEthHeaderWithProofByHash","params":{"hash": "0x8d0dd9b1f5854bbdc60d06aa04e6e953000aa53f6c6486f18f08666bc17ea228", "transcation": false, "options": {"format": "json"}}}' http://127.0.0.1:3000
```

## Trouble Shooting

Everytime you run `proof` in error, please delete `~/.ethashproof` and `~/.ethash` 
and retry.

## LICENSE

GPL-3.0


[infura]: https://infura.io
[github]: https://github.com/darwinia-network/darwinia.go
[spec]: https://github.com/darwinia-network/darwinia/wiki/Darwinia-offchain-worker-shadow-service-spec
[workflow-badge]: https://github.com/darwinia-network/darwinia.go/workflows/Golang%20CI/badge.svg
