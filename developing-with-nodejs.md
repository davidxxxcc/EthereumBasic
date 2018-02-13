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

Create a `Web3`instance using `ganche.provider`

```
const assert = require('assert');
const ganache = require('ganache-cli');

//to build Web3 constructor so that Web3 starts with upper letter.
const Web3 = require('web3');
const web3 = new Web3(ganache.provider());
```

### Mocha

Mocha is a testing framework

![](/assets/mochaFunctions)



