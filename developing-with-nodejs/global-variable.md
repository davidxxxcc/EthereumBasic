```
Block and Transaction Properties
block.blockhash(uint blockNumber) returns (bytes32): hash of the given block - only works for 256 most recent blocks excluding current
block.coinbase (address): current block miner’s address
block.difficulty (uint): current block difficulty
block.gaslimit (uint): current block gaslimit
block.number (uint): current block number
block.timestamp (uint): current block timestamp as seconds since unix epoch
msg.data (bytes): complete calldata
msg.gas (uint): remaining gas
msg.sender (address): sender of the message (current call)
msg.sig (bytes4): first four bytes of the calldata (i.e. function identifier)
msg.value (uint): number of wei sent with the message
now (uint): current block timestamp (alias for block.timestamp)
tx.gasprice (uint): gas price of the transaction
tx.origin (address): sender of the transaction (full call chain)
```

![](/assets/msg)[https://solidity.readthedocs.io/en/develop/units-and-global-variables.html\#special-variables-and-functions](https://solidity.readthedocs.io/en/develop/units-and-global-variables.html#special-variables-and-functions)

http://solidity.readthedocs.io/en/develop/units-and-global-variables.html

