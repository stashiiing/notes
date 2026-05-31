- author:: [[LiquidityGoblin]]
  summary:: A market-neutral carry strategy that simultaneously earns positive funding on short perpetual positions and staking or lending yield on the underlying spot asset, while accruing protocol points that convert to airdrop allocations. The combined yield can reach 28 to 40% annualised at meaningful size with manageable risk.
  category:: [[strategy]]
  sub-cat:: [[earn]], [[arbitrage]], [[discretionary]]
  timeframe:: [[swing]], [[position]]
  market:: [[crypto]]
  instrument:: [[spot]], [[perps]]
  tools:: [[HyperLiquid]], [[DeFi Llama]], [[Bybit]], [[Aave]]
  difficulty:: [[intermediate]]
  source:: https://www.youtube.com/watch?v=wm1P8im1fuE&t=2128s [35:28]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=wm1P8im1fuE&t=2128s}}
- # DeFi Carry Trade with Points Farming
- ## TL;DR
	- Go long staked spot and short the perpetual of the same asset to run market-neutral while collecting both the perpetual funding rate and the on-chain staking or lending yield. Layer protocol points on top by sizing and diversifying to maximise airdrop allocations. Rebalance approximately daily.
- ### Context
	- Perpetual DEXes frequently pay elevated positive funding on short positions during bullish market regimes. Many spot assets simultaneously offer staking or lending yield. Combining both sides creates a carry trade that is neutral to price direction, earning multiple yield streams. Protocols that reward open interest and risk-adjusted return (Sharpe) with points add a further compounding layer.
- ## Core Concept
	- Funding rate arbitrage: short the perp (collecting positive funding) while holding the spot asset long (earning staking or lending yield). The two positions cancel directional exposure. Net return is funding rate plus spot yield minus transaction and capital inefficiency costs.
- ## Mechanics
	- Screen perpetual DEXes for assets with persistently positive funding on the short side, targeting 20 to 30% annualised or above.
	- Cross-reference the underlying spot asset on DeFi Llama to identify staking, liquid staking, or lending opportunities on the same asset.
	- A classic example: short the perpetual at 11 to 20% funding, stake the spot for 20% staking yield, netting roughly 28% after accounting for capital inefficiency between the two legs.
	- For lending protocols on emerging chains, loop the native token through the chain's Aave fork to achieve leveraged long spot exposure at positive carry, then short on a centralised or decentralised perpetual venue to neutralise delta.
	- Size the portfolio across multiple assets and strategies to keep overall Sharpe high and increase points allocations on protocols that reward risk-adjusted returns.
	- Rebalance the hedge ratio approximately daily to account for funding rate changes and price drift between legs.
	- Monitor points programme mechanics: protocols that reward open interest multiplied by Sharpe incentivise diversified, hedged books over concentrated or unhedged ones.
- ## Entry / Trigger
	- Enter when annualised funding on the short perp side plus the staking or lending yield exceeds total round-trip transaction costs by a sufficient margin to justify the holding period. A practical threshold is a combined yield high enough to recover transaction costs within one to two weeks.
- ## Risk Management
	- Transaction costs on more liquid instruments can be 20 to 30 basis points per side; the trade must persist long enough to overcome this, typically more than one to two weeks.
	- Monitor for funding rate mean reversion: if funding flips negative on the short side, the carry becomes negative and the position should be closed or restructured.
	- Liquidation risk on the short perp leg if the spot asset rallies sharply; maintain sufficient margin or use lower leverage.
	- Protocol and smart contract risk on the staking or lending leg; diversify across protocols and avoid concentrating in unaudited or recently launched contracts.
	- Airdrop outcomes are uncertain; size the trade so it is profitable on yield alone without relying on points conversion.
- ## Examples
	- Cosmos (ATOM): staking yield of approximately 20% plus perpetual short funding of 11 to 20% produced a combined return of roughly 28% annualised at several million dollars in size.
	- HyperLiquid carry basket: a diversified portfolio of long staked spot and short perps, rebalanced daily, maintained a high Sharpe and accrued points that converted into a materially enhanced airdrop allocation compared with simple volume farming.
	- Emerging chain lending loops: native token deposited into the chain's lending protocol earning 6 to 8% base yield plus protocol token emissions, levered up, with the delta hedged on Bybit or HyperLiquid perps, producing 30 to 40% net carry.
- ## Caveats & Edge Cases
	- Trades with high funding rates often attract capital quickly, compressing the rate within days to weeks. Entry timing matters.
	- Points programmes change rules or end without notice; confirm programme mechanics before sizing up.
	- Capital inefficiency between the spot leg (on-chain, locked in staking) and the perp leg (on a centralised venue) means the effective return is lower than the sum of the two headline yields.
	- On emerging chains, DEX and bridge liquidity may make entry and exit slow and expensive, reducing net yield.
