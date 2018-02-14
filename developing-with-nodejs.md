### Start with npm project

```
npm init
```

### Genetae a compile.js file

Create a `compile.js`file and type codes as follows and export the module using `module.experts`.

Artcle regarding module export

[http://dreamerslab.com/blog/tw/node-js-basics/](http://dreamerslab.com/blog/tw/node-js-basics/)

```
const path = require('path');
const fs = require('fs');
const solc = require('solc');

const inboxPath = path.resolve(__dirname,'contracts','Inbox.sol');
const source = fs.readFileSync(inboxPath,'utf8');

module.exports = solc.compile(source, 1).contracts[':Inbox'];
```

### Solidity Compiler

`solc.compile` could be used to compile Solidify code into machine code. After compile finishing, there are two parts of content inside the contracts:

* Bytecode
* ABI

![](/assets/solidity compiler)

### Create a file `Inbox.test.js` in `test` folder

Create a `Web3`instance using `ganche.provider` and import the ABI interface & bytecode.

In `beforeEach `function we use `async `to assign `accounts `and create inbox instance from `web3.eth.Contract`.

Then we deploy  the contract by using `.deploy` and assign `bytecode `to generate contract and pass parameter`aruments `into the contructor.

```
const assert = require('assert');
const ganache = require('ganache-cli');
//to build Web3 constructor so that Web3 starts with upper letter.
const Web3 = require('web3');

const provider = ganache.provider();
const web3 = new Web3(provider);
const {interface, bytecode} = require('../compile');

let accounts;
let inbox;

beforeEach(async () => {
  // Get a list of all accounts
  accounts = await web3.eth.getAccounts();
  // Use one of those accounts to deploy the contract
  inbox = await new web3.eth.Contract(JSON.parse(interface))
    .deploy({ data: bytecode, arguments: ['Hi there!'] })
    .send({ from: accounts[0], gas: '1000000' });

  // ADD THIS ONE LINE RIGHT HERE!!!!! <---------------------
  inbox.setProvider(provider);
});

describe('Inbox', () => {
  it('deploys a contract', () => {
    assert.ok(inbox.options.address);
  });
  it('has a default message', async () => {
    const message = await inbox.methods.message().call();
    assert.equal(message, 'Hi there!');
  });

  it('can chang ethe message', async () => {
    await inbox.methods.setMessage('bye').send({ from: accounts[0] });
    const message = await inbox.methods.message().call();
    assert.equal(message, 'bye');
  });
});
```

### 



