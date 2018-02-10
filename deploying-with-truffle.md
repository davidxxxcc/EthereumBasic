#### What is Truffle

Truffle is an Ethereum development framework that will help us debugging, deploying, and testing smart contracts, among other things.

[http://truffleframework.com/docs/](http://truffleframework.com/docs/)

#### Get start with Truffle

The first thing we’re going to do is to deploy a contract using Truffle. Let's create a new directory for this exercise and run the following commands to install Truffle and initialize our project. We won’t need a testrpc node running since Truffle already comes with a simulation node for development and testing purposes.

```
$ mkdir truffle-experiment
$ cd truffle-experiment/
$ npm install truffle@4.0.4
$ npx truffle init
```

You will see some folders and files were created. Our directory should look like:

```
truffle-experiment/
├── contracts/
│ └── Migrations.sol
├── migrations/
│ └── 1_initial_migration.js
├── test/
├── truffle.js
└── truffle-config.js
```

The`contracts`folder is where the smart contracts should be. The`migrations`folder will host javascript files that will help us deploying our contracts to the network. You may also have seen a`Migrations`contract in the first folder, this is where the history of our migrations is going to be stored on-chain. The`test`folder is initially empty and is intended to keep our test files. Finally, you will see a`truffle.js`and a`truffle-config.js`files. We will skip them by now, but you can read more in [their documentation](http://truffleframework.com/docs/).

.Create `MyToken.sol` file inside the `contracts`folder and we can use the example of [token contract](https://blog.zeppelin.solutions/a-gentle-introduction-to-ethereum-programming-part-2-7bbf15e1a953#9b33).

Then, create a new migration file called`2_deploy_my_token.js`file in migration folder and copy the following lines into it:

```
const MyToken = artifacts.require('./MyToken.sol')
module.exports = function(deployer) {
  deployer.deploy(MyToken)
}
```

Truffle already comes with a simulation node for development and testing purposes. We just need to open a development console running`npx truffle develop`and run the migrations using`truffle migrate`inside it. Then, you should see an output like this:

```
truffle(develop)
>
 truffle migrate
Using network ‘develop’.
Running migration: 1_initial_migration.js
Deploying Migrations…
… 0xf5776c9f32a9b5b7600d88a6a24b0ef433f559c31aaeb5eaf6e2fc5e2f7fa669
Migrations: 0x8cdaf0cd259887258bc13a92c0a6da92698644c0
Saving successful migration to network…
… 0xd7bc86d31bee32fa3988f1c1eabce403a1b5d570340a3a9cdba53a472ee8c956
Saving artifacts…
Running migration: 2_deploy_my_token.js
Deploying MyToken…
… 0xc74019c2fe3b3ef1d4e2033c2e4b9fa13611f3150f8b6b37334a8e29e24b056c
MyToken: 0x345ca3e014aaf5dca488057592ee47305d9b3e10
Saving successful migration to network…
… 0xf36163615f41ef7ed8f4a8f192149a0bf633fe1a2398ce001bf44c43dc7bdda0
Saving artifacts…
```

We’ll just care about the line`MyToken: 0x345ca3e0...305d9b3e10`, which tells us the address of our deployed token contract. By default, Truffle initializes the simulation node with 10 addresses with fake ETH as we saw when using`testrpc`, and we can access this array via`web3.eth.accounts`. Moreover, it deploys these contracts using the first address of this list \(the one with index 0\), which means that it will be the owner of`MyToken`.

Given that`Web3`is available inside the Truffle console, you can just run the following commands to check the owner’s balance:

```
truffle(develop)>
owner = web3.eth.accounts[0]
truffle(develop)>
instance = MyToken.at('[DEPLOYED_ADDRESS]')
truffle(develop)>
instance.balanceOf(owner)
```





