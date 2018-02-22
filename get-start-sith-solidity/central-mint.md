### CENTRAL MINT

Suppose you want the amount of coins in circulation to change. This is the case when your tokens actually represent an off blockchain asset \(like gold certificates or government currencies\) and you want the virtual inventory to reflect the real one. This might also be the case when the currency holders expect some control of the price of the token, and want to issue or remove tokens from circulation.

First, we need to add a variable to store the **totalSupply **and assign it to our constructor function.

```
    contract MyToken {
        uint256 public totalSupply;

        function MyToken(...) {
            totalSupply = initialSupply;
            ...
        }
        ...
```

Now let's add a new function finally that will enable the owner to create new tokens:

```
    function mintToken(address target, uint256 mintedAmount) onlyOwner {
        balanceOf[target] += mintedAmount;
        totalSupply += mintedAmount;
        Transfer(0, owner, mintedAmount);
        Transfer(owner, target, mintedAmount);
    }
```



