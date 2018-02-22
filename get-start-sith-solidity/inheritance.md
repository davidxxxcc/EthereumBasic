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



