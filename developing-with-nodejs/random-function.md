### Why 

there's no random function in Solidity.

### How to generate random function

We can use `keccak256()` to ceate very big random number.

```
keccak256(...) returns (bytes32):
compute the Ethereum-SHA-3 (Keccak-256) hash of the (tightly packed) arguments
```

http://solidity.readthedocs.io/en/develop/units-and-global-variables.html



```
pragma solidity ^0.4.17;

contract Lottery{
    address public manager;
    address[] public players;
    
    function Lottery() public {
        manager = msg.sender;
    }
    
    function enter() public payable {
        require(msg.value > .01 ether);
        players.push(msg.sender);
    }
    
    function random() private view returns (uint) {
        return uint(keccak256(block.difficulty, now, players));
    }
    
}
```



