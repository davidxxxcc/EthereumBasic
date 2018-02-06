**Ethereum**

Let’s start by defining Ethereum, or at least, what I understood about it after my research. Ethereum is an open-source public platform, distributed and based on blockchain technology, to run applications without censorship or third-party interference.

**Smart Contracts**

Smart contracts are just computer programs. We build Ethereum applications based on smart contracts. Bear in mind that even though this concept comes up with Ethereum these days, it was actually proposed by Nick Szabo in 1996 :\)

**Ethereum Virtual Machine**

The EVM is the sandboxed runtime and completely isolated environment for smart contracts in Ethereum. This means every smart contract running inside the EVM has no access to network, file system or other processes.

**Gas**

Given that Ethereum is a distributed platform, there must be a way to limit the resources available to a given smart contract, otherwise it could starve the whole network’s computing power. Gas solves that issue by fixing a cost for every instruction executed in the EVM. One important thing, is that every transaction is sent to the network with a “gas budget”. If it runs out, the transaction will fail but still gets mined into the blockchain.

**Ether \(ETH\)**

It is the Ethereum cryptocurrency token. There is a gas/Ether dynamic price that measures how much ETH will an operation cost. The fee paid to execute a transaction is calculated by multiplying the gas cost and the gas price \(the resulting fee is paid in ETH\). You can set the gas price for your transaction to any value. However, if the gas price is too low, no one is going to execute your code.

**Accounts**

Every account is identified by an address. There are two kinds of accounts sharing the same address space. On one hand, we have external accounts controlled by public-private key pairs, commonly owned by people to store ETH. On the other hand, we have contract accounts that are controlled by the code that it’s stored with it. These have a few differences, but one very important to have in mind, is that only external accounts can initiate transactions.

**Transactions**

A transaction is a message sent from one account to another account. You can send a transaction to another external account in order to transfer ETH. If the target account is a contract account, its code will be executed as well. Note that every transaction that involves code execution will be executed on all nodes of the network. Furthermore, every code run, or transaction execution, will be recorded in the Ethereum blockchain.

**Solidity**

Solidity is a contract-oriented high-level language, with similar syntax to JavaScript. It is statically typed, supports inheritance, libraries and complex user-defined types. It compiles to EVM assembly, which is run by the nodes.

