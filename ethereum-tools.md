#### **testrpc**

testrpc is a fast Ethereum RPC client for testing and development

You will notice that `testrpc`has generated 10 addresses with fake ETH you can use without the need to worry about them. This is how `testrpc`works by default, but you can make a custom initialization following the documentation. It’s important to mention that `testrp`state is volatile, that is every time you close it, the state of your node and accounts will be cleared.

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

[https://github.com/ethereum/wiki/wiki/JavaScript-API](https://github.com/ethereum/wiki/wiki/JavaScript-API)

First of all, you need to connect Web3 with your local testing node you are running with`testrpc.`In order to do that, we will ask Web3 to use a localhost provider. Let’s open a node console and input following lines:

```
Web3 = require('web3')
```

```
provider = new Web3.providers.HttpProvider("http://localhost:8545")

web3 = new Web3(provider)
```



