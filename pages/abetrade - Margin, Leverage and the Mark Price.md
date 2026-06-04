- author:: [[abetrade]]
  summary:: Crypto perpetuals let traders set their own leverage via a margin slider, unlike traditional futures where leverage is baked into a fixed contract size. Initial margin opens the position; maintenance margin is the floor below which liquidation is triggered. Liquidation is measured against the mark price (a manipu-resistant composite reference price) rather than the last traded price, which explains why positions can survive apparent wick-downs on the chart.
  category:: [[concept]]
  sub-cat:: [[orderflow]]
  timeframe::
  market:: [[crypto]]
  instrument:: [[perps]]
  tools::
  difficulty:: [[intermediate]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Margin, Leverage and the Mark Price
- ## TL;DR
	- In crypto perpetuals, leverage is a slider the trader controls directly, and it simply determines how much initial margin is required. Maintenance margin is the floor below which a position is liquidated. Crucially, liquidation is not triggered by the last traded price on the chart but by the mark price, a manipul-ation-resistant composite derived from multiple spot venues. This is why positions can survive a wick to their apparent liquidation level and why a single thin venue cannot be used to trigger liquidations the broader market does not agree with.
- ### Context
	- Misunderstanding how margin and liquidation work in crypto perps leads to both over-leveraging and confusion about why positions are or are not liquidated. The mark price mechanism is also a key difference from traditional futures that traders coming from other markets need to understand.
- ## Core Concept
	- Leverage and initial margin are two sides of the same dial: at 40x leverage, initial margin is 2.5% of notional. Higher leverage means less room to be wrong before hitting the maintenance margin floor. Exchanges scale margin requirements with position size via leverage tiers, so very large positions face lower maximum leverage and higher maintenance margin requirements.

	  The mark price (on Binance) is the median of three values: a spot index, that index adjusted by the current funding basis, and the contract's own last price. The spot index is itself a weighted average across multiple major exchanges with a guard against any single source deviating too far. Unrealised P&L and liquidation levels are both measured against the mark, never the last print.
- ## Mechanics
	- Initial margin: the collateral required to open a position. At 40x, Hyperliquid requires 2.5% of notional upfront.
	- Maintenance margin: the minimum equity floor. On Hyperliquid it is half the initial margin for a given tier. A 40x position is liquidated when equity falls to 1.25% of notional.
	- Isolated margin: a fixed amount of collateral is ring-fenced for one position. Liquidation of that position does not touch the rest of the account.
	- Cross margin: the entire account balance backs all open positions. Unrealised profit on one trade supports another. Liquidation only triggers when total account equity falls below combined maintenance margin across all positions, but a failure wipes the whole account rather than a single position.
	- Exchanges liquidate in stages (trimming rather than dumping) where size and liquidity allow.
	- When a position cannot be closed for enough to cover losses, the insurance fund absorbs the shortfall. If the insurance fund is exhausted, auto-deleveraging (ADL) forces profitable traders on the opposite side to close out to cover the bankrupt position, ranked by profit and leverage.
- ## Caveats & Edge Cases
	- ADL means a trader can be on the right side of a trade, deep in profit, and still be closed out involuntarily so the exchange can stay solvent. This does not happen in cleared traditional futures markets.
	- The mark price protects against single-venue manipulation but cannot prevent a sufficiently large or coordinated attack on the spot index itself.
	- Cross margin is more capital-efficient and survives deeper drawdowns, but when it finally breaks it takes the entire account rather than one position.
