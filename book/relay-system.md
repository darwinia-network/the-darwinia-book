# Relay System

As a bridge chain based on substrate, `Relay System` is the core feature of `Darwinia`.

Currently we supports relaying `RING` token of Ethereum into Darwinia, the process is like:

```
               Redeem          Deposit
     
User        -> Contract     -> Contract

- - - - - - - - - - - - - - - - - - - - < Darwinia

Relayer     -> Handle       -> Handle
```

As contributers of Darwinia, we need to know the concreted implementation of the relay system,
how could we mock this?

Assume that you have already set up your Darwinia development node, we also need [Shadow](./shadow.md) and [DJ](./dj.md) which are the data service and the relayer tool.

Fine, Let's go to the next chapter.
