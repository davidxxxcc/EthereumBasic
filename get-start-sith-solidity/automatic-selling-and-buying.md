So far, you've relied on utility and trust to value your token. But if you want you can make the token's value be backed by Ether \(or other tokens\) by creating a fund that automatically sells and buys them at market value.

First, let's set the price for buying and selling:

```
    uint256 public sellPrice;
    uint256 public buyPrice;

    function setPrices(uint256 newSellPrice, uint256 newBuyPrice) onlyOwner {
        sellPrice = newSellPrice;
        buyPrice = newBuyPrice;
    }
```

This is acceptable for a price that doesn't change very often, as every new price change will require you to execute a transaction and spend a bit of Ether. If you want to have a constant floating price we recommend investigating[standard data feeds](https://github.com/ethereum/wiki/wiki/Standardized_Contract_APIs#data-feeds)

The next step is making the buy and sell functions:

```
    function buy() payable returns (uint amount){
        amount = msg.value / buyPrice;                    // calculates the amount
        require(balanceOf[this] >= amount);               // checks if it has enough to sell
        balanceOf[msg.sender] += amount;                  // adds the amount to buyer's balance
        balanceOf[this] -= amount;                        // subtracts amount from seller's balance
        Transfer(this, msg.sender, amount);               // execute an event reflecting the change
        return amount;                                    // ends function and returns
    }

    function sell(uint amount) returns (uint revenue){
        require(balanceOf[msg.sender] >= amount);         // checks if the sender has enough to sell
        balanceOf[this] += amount;                        // adds the amount to owner's balance
        balanceOf[msg.sender] -= amount;                  // subtracts the amount from seller's balance
        revenue = amount * sellPrice;
        msg.sender.transfer(revenue);                     // sends ether to the seller: it's important to do this last to prevent recursion attacks
        Transfer(msg.sender, this, amount);               // executes an event reflecting on the change
        return revenue;                                   // ends function and returns
    }
```

Notice that this will not create new tokens but change the balance the contract owns. The contract can hold both its own tokens and Ether and the owner of the contract, while it can set prices or in some cases create new tokens \(if applicable\) it cannot touch the bank's tokens or Ether. The only way this contract can move funds is by selling and buying them.

**Note**Buy and sell "prices" are not set in Ether, but in_wei_the minimum currency of the system \(equivalent to the cent in the Euro and Dollar, or the Satoshi in Bitcoin\). One Ether is 1000000000000000000 wei. So when setting prices for your token in Ether, add 18 zeros at the end.

When creating the contract,**send enough Ether to it so that it can buy back all the tokens on the market**otherwise your contract will be insolvent and your users won't be able to sell their tokens.

The previous examples, of course, describe a contract with a single central buyer and seller, a much more interesting contract would allow a market where anyone can bid different prices, or maybe it would load the prices directly from an external source.

