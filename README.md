Smart contract for upvsdown.com game from Playnance (https://playnance.com)

The game available on https://upvsdown.com

The smart contract address on Polygon Mainnet (V2 Contract): 
https://polygonscan.com/address/0x7a7726273407287c7926bd177f482d1442a79d27

The smart contract address on Polygon Mainnet (V3 Contract): 
https://polygonscan.com/address/0x4b8C7cCa34FEe91bce95bb7cfc413fca2a193AC7

V3 Changes:
1. UVD-13 | Unused Contract and Library
Remove the String library declaration

2. UVD-12 | Comparison to Boolean Constant
When creating pool (CreatePool function) there is no need for boolean comparison.
How to test: Check that create pool function works correctly when restarting game controller service.

3. UVD-09 | The default winner is `downBetGroup`
In case of TIE the bets investments should be returned to both groups.
TIE case is when startPrice = endPrice
The special case for money return is when
* startPrice = endPrice (TIE)
* one of the pools are empty

4. UVD-05 | Missing Zero Address Validation
These addresses cannot be empty and must not accept zero address
* Game controller address
* Fee address
* Jackpot address

5. UVD-03 | No Upper Limit in `changeGameFeePercentage` function
Upper limit for fee percentage should be 100
This limit implemented also to jackpot fee percentage

6. Fix rounding when calculating wining.

7. Add fee percentage and jackpot fee percentage to TradeWinningsSent

8. Jackpot feature - There are 2 fees that sent to the system:
* System Fee (9%)
* Jackpot Fee (1%)
