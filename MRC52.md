# MRC52 - Possibility to add yields from tokens other than stETH

The current protocol works for stETH staking, this documentation was created to consider adding other stake tokens to the Distribution contract such as USDC, USDT, BTC, SOL.

## The existing stake token - stETH

The stETH is a rebaseable token, users stake this token and based on the stake, receive a reward in MOR token, which is distributed proportionally to the stake taking into account various multipliers.

The stETH yield itself is separate from the logic of reward calculation and is calculated automatically by the stETH token itself. The protocol owner uses this yield to increase the liquidity pool for the MOR token in the Arbitrum network.

## Main areas to be considered

1. Adding a new stake token and using it in lending protocols to generate yield. We need to consider protocols for yield and mechanics that will allow users to interact with them within our protocol.
2. Changing the mechanics of reward distribution between users. When adding new tokens, the market price will be different, so it is necessary to introduce additional coefficients based on the exchange rate.
3. Updating the current protocol and ensuring data integrity for existing users.

# Yield for the new stake tokens

The plan is to use the [Aave](https://aave.com/) lending protocol for yield. 

User stake tokens will be deposited in the protocol, and interest (yield) will be accrued on the funds. The amount of yield depends on the lending protocol itself and is not regulated by the current protocol.

The yield will be used by Morpheus to increase the liquidity of the MOR token or other needs of the project at the discretion of the owner of the Morpheus protocol. It is planned to transfer the yield to the Arbitrum network, just like with stETH.

The risks associated with the Aave protocol itself are also not covered by the current protocol, like:

- A sharp increase in borrowing - if many people are borrowing at the same time.
- Liquidity crisis - for example, a market panic or a failure in the protocol.
- Attacks on the protocol - if someone manipulates liquidity.

# Mechanics of reward distribution between users

## How it works now

There is a library in the protocol that calculates how much MOR should be allocated to all users. This amount depends only on time and decreases every day. **This logic will remain unchanged.**

The user stakes stETH, multipliers (Power Factor, Referal Progeam) are applied to the final user stake amount, so we are ahead of the user's `virtual stake`.

Rewards for a certain period (which depends on user transactions) are distributed proportionally among users based on their `virtual stake`. The larger the `virtual stake`, the more rewards the user will receive.

## How's this gonna work?

For each new stake token, a smart contract will be deployed, like `Distribution Contract USDC` or `Distribution Contract WBTC` that will contain the yield calculation logic for the current token.
All such contracts will use one `Reward Calculator Contract` that will distribute rewards among other smart contracts.

![image.png](attachment:2d31bdb8-dbc2-4f91-8b01-c8a850b1c6e4:image.png)

The `Reward Calculator Contract` must, for correct calculations, contain `rate` that will be applied when calculating the share of the reward for each smart contract. The `rate` will be formed based on the exchange rate to one currency, for example USDC.

The exchange rates will be updated every time we need to calculate rewards (stake, withdrawal). **Data will be taken from one of the decentralized sources, like Uniswap or ChainLink.**

It should be understood that all stakers will receive rewards at the current `rate` specified in the smart contract. That is, for example, if the BTC exchange rate rises sharply, the `rate` will not be updated until the transaction mentioned above is carried out within the current protocol.

Adding new tokens will require the deployment of a new group of `Distribution Contract`. This architecture will allow adding new tokens without problems, but the total number of stake tokens added may be limited because the reward calculation must be done for each new token, which increases transaction costs.

# Updates to the current Distribution protocol

We believe that the fewer changes to the existing protocol, the better.

It is assumed that the logic for calculating rewards will be transferred to the  `Reward Calculator Contract`. In this way we will practically not affect information about user stakes and other smart contract information.

# Chainlink Price Feed

We may use the Chainlink Price Feed to receive up-to-date rates. Documentation for the integration can be found [here](https://docs.chain.link/data-feeds/using-data-feeds#overview). Chainlink does not charge LINK for such requests.
Based on the [list of supported pairs](https://docs.chain.link/data-feeds/price-feeds/addresses?network=ethereum), it is recommended to use `USDC` as a common currency for all pairs. 

For example: `stETH -> USDC`, `BTC -> USDC`, `SOL→USD`.

# AAVE protocol

The Morpheus Protocol will act as a liquidity provider on behalf of all Stakers.

**Stake**
When users stake, the Morpheus protocol deposits for example `USDC` into Aave and receives `aToken`.
*For example by stake `100 USDC` the user will receive `100 aToken`.*

**Withdraw**

When the user wants to withdraw `USDC`, we calculate the price of `aToken` relative to `USDC`, return `USDC`, and leave the remainder to Morpheus protocol.
*For example, at the moment of withdrawal transaction `1 aToken costs 1.2 USDC`. Thus `1 USDC costs 0.83 aToken`. The user has deposited `100 USDC` to be returned, which is `83.33 aToken`. Change `83.33 aToken * 1.2` and return `100 USDC` to the Staker. Then the Morpheus protocol can exchange the remaining `16.66 aToken` for USDC and get `20 USDC` .*

The contract will include features that will calculate the profitability of the Morpheus protocol.
