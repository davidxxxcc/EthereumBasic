### Start with npm project

```
npm init
```

### Genetae a compile.js file

Create a `compile.js `file and type codes as follows and export the module using `module.experts`.

Artcle regarding module export

http://dreamerslab.com/blog/tw/node-js-basics/

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
