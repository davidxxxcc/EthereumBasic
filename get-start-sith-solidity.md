### Ethereum Virtual Machine \(EVM\)

The EVM allows Ethereum nodes to actually store and process data in exchange for payment, responding to real-world events and allowing a lot of new opportunities to support on-chain applications that were never before available to developers and real-world users.

### Ethereum smart contract

Smart-contract are a way for people all across the globe to do business with each other even if they don't speak the same language or use the same currency.

* Have data and code
* Have balance and address
* Functions invoked by sending transactions
* Ouput returned after transactions mined

### Solidity language

Solidity language itself is a tool that we use to generate machine-level code that can execute on the EVM, it's a language with a complier which takes our high-level human-readable code and breaks it down into simple instructions like "put data into a register", "add data from two registers", "jump back to instruction at memory point xxxx", which form the basis of any microprcessor executable program.

Let's see example 1. The constructor `Hodor`is only invoked only once when the contract that is first deployed on the Ethereum block chain. You can only declare a single contructor for a contract. `msg`.is a global variable and we declare `address`and `string`type of data. Function `greeting`return a constant `string`type while function `setGreeting`only accpet passing `string`type variabble.

example 1

```
pragma solidity ^0.4.0

contract Hodor {
    address creator;
    string greeting;

    function Hodor(string _greeting) {
        greeting = _greeting;
        creator = msg.sendor;
    }

    function greet() constant returns (string) {
        return greeting;
    }

    function setGreeting(string _greeting) {
        greeting = _greeting;
    }
}
```

As we can see, we delare `creator`with `public`that allows contracts to acces the current value of field such as `creator()`; Without `public`keyword, no contract could access the value. the `mapping`is like a hash table of key value pairs. The key value data types are defined inside the brackets `()`as `address`keys mapping  to unsigned integer values `uint.`representing the amount owned by an address. `event`are listening some interest of happening and can be listened to either server side or front end. As soon as `Delivered`is fired, this function will deliver `from`, `to`and `amount`.

`throw`keyword will early return the function if the statement is `true`.

example 2

```
pragma solidity ^0.4.0;

contract DragonStone {
    address public creator;
    mapping (address => uint) public balance;

    event Delivered(address from, address to, uint amount);

    function DragStone() {
        creator = msg.sender;
    }

    function create(address receiver, uint amount) {
        if(msg.sender != creator) throw;
        balance[receiver] += amount;
    }

    function transfer(address receiver, uint amount) {
        if(balance[msg.sender] < amount) throw;
        balance[msg.sender] -= amount;
        balance[receiver] += amount;
        Delivered(msg.sender, receiver, amount);
    }

}
```



