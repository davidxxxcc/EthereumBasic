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



