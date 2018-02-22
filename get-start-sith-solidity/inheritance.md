### Inheritance

Inheritance allows a contract to acquire properties of a parent contract, without having to redefine all of them. This makes the code cleaner and easier to reuse. Add this code to the first line of your code, before **contract MyToken {**.

```
    contract owned {
        address public owner;

        function owned() {
            owner = msg.sender;
        }

        modifier onlyOwner {
            require(msg.sender == owner);
            _;
        }

        function transferOwnership(address newOwner) onlyOwner {
            owner = newOwner;
        }
    }
```



This creates a very basic contract that doesn't do anything except define some generic functions about a contract that can be "owned". Now the next step is just to add the text _is owned _to your contract:

```
    contract MyToken is owned {
        /* the rest of the contract as usual */
```



