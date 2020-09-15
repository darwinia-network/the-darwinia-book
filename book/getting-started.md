# Getting Started



## Download

You can download the latest darwinia node from the latest [release][download].

## Run the Node

```
$ ./darwinia --dev
```

As developers, we strongly recommend you guys to clean the storge every you run the node,
keep our node clean, for example:

```
$ rm -rf tmp && ./darwinia --dev -d tmp
```

## Chain Status

You can visit [Apps][apps] and set the node address to your local node to view the chain status.

### Note

Don't forget to update the `types.json` of your node, you can find the latest one [here][types.json].

[apps]: https://apps.darwinia.network/#/account
[download]: https://github.com/darwinia-network/darwinia/releases
[types.json]: https://github.com/darwinia-network/darwinia-common/blob/master/bin/node-template/runtime/darwinia_types.json
