- author:: [[abetrade]]
  summary:: Perpetual futures come in two main settlement flavours: linear contracts settle in a stablecoin (USDT/USDC) and produce a straightforward dollar-denominated P&L, while inverse contracts settle in the underlying coin and produce a non-linear payoff. Linear contracts are the standard for nearly all trading today; inverse contracts survive among traders who want their entire stack denominated in one coin.
  category:: [[concept]]
  sub-cat:: [[orderflow]]
  timeframe::
  market:: [[crypto]]
  instrument:: [[perps]], [[futures]]
  tools::
  difficulty:: [[beginner]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Linear vs Inverse Perpetual Contracts
- ## TL;DR
	- The only real difference between linear and inverse perpetuals is what currency settles the trade. Linear contracts settle in a stablecoin, making P&L straightforward: one dollar of price movement equals one dollar of gain or loss. Inverse contracts settle in the underlying coin while quoting in dollars, which bends the payoff curve. For most traders, linear contracts are the default and inverse contracts are a historical relic with a narrow use case.
- ### Context
	- Choosing the wrong contract type can produce unexpected P&L behaviour, particularly under leverage. Understanding the settlement mechanics prevents confusion when sizing positions or measuring risk.
- ## Core Concept
	- Linear contracts: Quote and settlement are the same currency (usually USDT). P&L scales linearly with price movement. This is what traders use the vast majority of the time.

	  Inverse contracts: The chart is quoted in USD but collateral and settlement are in the underlying coin (e.g., BTC). Because the collateral itself is moving against the dollar, the payoff is non-linear. An equal-size long and short do not carry the same coin-denominated risk. These contracts originated on BitMEX and now survive mainly among traders who prefer to keep their entire stack in one coin.

	  Quanto contracts settle in a currency unrelated to either leg, bending the payoff even further. They are rarely traded and can be ignored for practical purposes.
- ## Mechanics
	- For linear contracts: P&L = (Exit Price − Entry Price) × Position Size. Straightforward and predictable.
	- For inverse contracts: P&L is denominated in the coin, so a 10% move in BTC price does not translate to a 10% change in coin-denominated P&L when the coin itself is moving against the dollar. Gains and losses do not scale evenly with price.
	- Collateral choice matters: a linear account uses stablecoins as margin; an inverse account uses the underlying coin as margin, exposing the margin itself to price moves.
- ## Caveats & Edge Cases
	- Inverse contracts can produce unexpected losses even when the directional call is correct, because the coin-denominated collateral is simultaneously moving against the trader.
	- Liquidity in inverse contracts is thinner than in linear equivalents on most modern exchanges, which increases slippage.
