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

.Create `MyToken.sol` file inside the `contracts `folder and we can use the example of [token contract](https://blog.zeppelin.solutions/a-gentle-introduction-to-ethereum-programming-part-2-7bbf15e1a953#9b33).

Then, create a new migration file called`2_deploy_my_token.js`file in migration folder and copy the following lines into it:

```
const MyToken = artifacts.require('./MyToken.sol')
module.exports = function(deployer) {
  deployer.deploy(MyToken)
}
```





