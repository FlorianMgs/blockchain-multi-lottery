# Solidity Multi Lottery
This project is a Blockchain lottery made in Solidity.  
Contract is not yet audited / checked with Slither. Use it with caution.  
## Usage
Deploy this contract on any EVM blockchain.  
When deployed, you'll have to create lotteries by calling createLottery with a minimum entry price and a maximum entry price.  
Each player can enter only once per draw by activating enter with a price between lotteryPriceMin and lotteryPriceMax.  
Player cannot enter if lottery is paused.  
He get lotteryPriceMax / lotteryPriceMin tickets.  
Only owner of contract can draw a winner by supplying an int as salt when triggering pickWinner.  
Using a salt should make the function miner resistant.  
I will maybe add Chainlink support to get a truly random number.  
When winner is drawn, a fee is sent to owner (5% of pot by default) and lottery state is resetted. Winner is saved in lotteryHistory mapping.  