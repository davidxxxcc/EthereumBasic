#### What is Truffle

Truffle is an Ethereum development framework that will help us debugging, deploying, and testing smart contracts, among other things.

http://truffleframework.com/docs/



#### Get start with Truffle

The first thing we’re going to do is to deploy a contract using Truffle. Let's create a new directory for this exercise and run the following commands to install Truffle and initialize our project:

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



