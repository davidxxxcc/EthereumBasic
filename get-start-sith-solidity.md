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

### data type

`Uint256`

* [unsigned](https://en.wikipedia.org/wiki/Signedness)\(meaning this type can only represent positive integers, \_not \_positive **and **negative integers\)
* `INT`- integer
* `256`- 256 bits in size

### ![](/assets/basicTypes)![](/assets/int)![](/assets/uint)

### Reference Type

string is a array in Solidity.

we couldn't declare `["ABC","CDR"]` in Soidlity

![](/assets/reftype)

### Function Type

### ![](/assets/function format)![](/assets/function type)

### Difference between Calling a Function and Sending a Transaction to a Function

Let's see the below example code and the running contract functions.

If we want to change data in Ethereum block chain, this action need to generate a transaction to finish.

```
pragma solidity ^0.4.17;
contract Inbox {
    string public message;

    function Inbox(string initialMessage) public {
        message = initialMessage;
    }

    function setMeesage(string newMeesage) public {
        message = newMeesage;
    }

}
```

![](/assets/running function)

### Boilerplate Design in Solidity![](/assets/Boilerplate Design)

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

Funciton of Solidity cannot accept or return two dimensional arrays. the string data type of array is implemented as an array of the bytes32 data type.

```
function Election(string name, uint durationMinutes, string[] candidateNames) {

}
```

Finally, we now need something called **Events**. These are special, empty functions that you call to help clients like the Ethereum Wallet keep track of activities happening in the contract. Events should start with a capital letter. Add this line at the beginning of the contract to declare the event:

```
event Transfer ( address indexed from, address indexed to, uint256 value);
```

### msg.value

This is what the crontact receive in ethereum \(what the sender of the transaction pay exclude gas and miner fee\). It is in wei \(1 ethereum = 10000000000000000000 wei \(10^18\)\) wei is like satoshi a subunit more precise.

It is part of the transaction, from the Ethereum Yellow Paper, section 4.2 "The transaction" it has a field named 'value'.

From a contract you get the value with the opcode CALLVALUE \(0x34\), section H.2 "Instruction Set", table "30s Environmental Information".



`msg.value`is the amount of ETH sent to a`payablepublic`method in a contract.

`this.balance`is the amount of ETH stored in the contract.

