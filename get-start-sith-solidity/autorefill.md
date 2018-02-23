Everytime, you make a transaction on Ethereum you need to pay a fee to the miner of the block that will calculate the result of your smart contract.[While this might change in the future](https://github.com/ethereum/EIPs/issues/28), for the moment fees can only be paid in Ether and therefore all users of your tokens need it. Tokens in accounts with a balance smaller than the fee are stuck until the owner can pay for the necessary fee. But in some use cases, you might not want your users to think about Ethereum, blockchain or how to obtain Ether, so one possible approach would have your coin automatically refill the user balance as soon as it detects the balance is dangerously low.

In order to do that, first you need to create a variable that will hold the threshold amount and a function to change it. If you don't know any value, set it to**5 finney \(0.005 Ether\)**.

```
    uint minBalanceForAccounts;

    function setMinBalance(uint minimumBalanceInFinney) onlyOwner {
         minBalanceForAccounts = minimumBalanceInFinney * 1 finney;
    }
```



