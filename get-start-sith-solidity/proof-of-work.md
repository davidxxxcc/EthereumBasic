#### PROOF OF WORK {#proof-of-work}

There are some ways to tie your coin supply to a mathematical formula. One of the simplest ways would be to make it a "merged mining" with Ether, meaning that anyone who finds a block on Ethereum would also get a reward from your coin, given that anyone calls the reward function on that block. You can do it using the [special keyword coinbase](https://solidity.readthedocs.io/en/latest/units-and-global-variables.html#block-and-transaction-properties) that refers to the miner who finds the block.

```
    function giveBlockReward() {
        balanceOf[block.coinbase] += 1;
    }
```

It's also possible to add a mathematical formula, so that anyone who can do math can win a reward. On this next example you have to calculate the cubic root of the current challenge gets a point and the right to set the next challenge:

```
    uint currentChallenge = 1; // Can you figure out the cubic root of this number?

    function rewardMathGeniuses(uint answerToCurrentReward, uint nextChallenge) {
        require(answerToCurrentReward**3 == currentChallenge); // If answer is wrong do not continue
        balanceOf[msg.sender] += 1;         // Reward the player
        currentChallenge = nextChallenge;   // Set the next challenge
    }
```



