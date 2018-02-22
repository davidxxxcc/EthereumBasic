Depending on your use case, you might need to have some regulatory hurdles on who can and cannot use your tokens. For that to happen, you can add a parameter that enables the contract owner to freeze or unfreeze assets.

Add this variable and function anywhere inside the contract. You can put them anywhere but for good practice we recommend you put the mappings with the other mappings and events with the other events.

```
    mapping (address => bool) public frozenAccount;
    event FrozenFunds(address target, bool frozen);

    function freezeAccount(address target, bool freeze) onlyOwner {
        frozenAccount[target] = freeze;
        FrozenFunds(target, freeze);
    }
```

With this code, all accounts are unfrozen by default but the owner can set any of them into a freeze state by calling **Freeze Account **. Unfortunately, freezing has no practical effect because we haven't added anything to the transfer function. We are changing that now:

```
 function transfer(address _to, uint256 _value) {
        require(!frozenAccount[msg.sender]);
```



