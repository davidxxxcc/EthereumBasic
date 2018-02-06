#### **testrpc**

testrpc is a fast Ethereum RPC client for testing and development

You will notice that `testrpc `has generated 10 addresses with fake ETH you can use without the need to worry about them. This is how `testrpc `works by default, but you can make a custom initialization following the documentation. It’s important to mention that `testrp `state is volatile, that is every time you close it, the state of your node and accounts will be cleared.

```
npm install -g ethereumjs-testrpc
```

```
testrpc
```

[http://www.jsonrpc.org/specification](http://www.jsonrpc.org/specification)

#### Web3 module

web3.js works with any Ethereum node, which exposes an RPC\(remote procedure call\) layer.

It is a JavaScript library that implements the Ethereum JSON RPC. That is, the protocol that we will use to talk to an Ethereum node \(in this case, testrpc\). To install it, just run:

```
npm install -g web3@0.20.1
```



