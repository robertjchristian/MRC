# Protocol Owned Liqudity Update 2024 10 30

## Context: Each time the PoL buys tokens from the Uniswap pool on Arbitrum it burns 1/3, locks 1/3 and sets a "full range" LP position in the pool with the last 1/3.

## Change: Instead of the "full range" position, this proposal is to set the LP position at the current price to 5% higher than the current price.

For example if the price of MOR is $20 at the time of the Protocol Owned Liquidiy LP deployment, the LP range will be set from $20 to $21. 

## Benefits: 
- 1. Those wanting to buy MOR will have access to more concentrated liquidity closer to the market place.
- 2. This approach will reduce the slippage for those buying MOR.
  
