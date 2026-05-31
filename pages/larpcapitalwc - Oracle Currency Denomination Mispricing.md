- author:: [[larpcapitalwc]]
  summary:: Crypto perp platforms that list equity or commodity perps rely on oracles to price the underlying. When the oracle's denomination currency changes (e.g. USD to GBP), the reported price jumps by the FX rate even though the asset's intrinsic value is unchanged. Traders who are short at the moment of the switch are liquidated by an artificial price move. The strategy involves identifying upcoming denomination changes or analogous oracle update events and positioning accordingly.
  category:: [[strategy]]
  sub-cat:: [[arbitrage]], [[systematic]]
  timeframe:: [[intraday]]
  market:: [[crypto]], [[equities]]
  instrument:: [[perps]]
  tools::
  difficulty:: [[advanced]]
  source:: https://www.youtube.com/watch?v=I23nncSxN3M&t=2754s [45:54]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=I23nncSxN3M&t=2754s}}
- # Oracle Currency Denomination Mispricing
- ## TL;DR
	- When a crypto perp platform changes the currency denomination of an oracle (for example from USD to GBP), the price feed jumps by the prevailing FX rate. This is not a real move in the underlying asset but it is a real liquidation event for anyone short. Anticipating these scheduled or predictable oracle transitions creates a structural long opportunity with a known catalyst.
- ### Context
	- Crypto perp platforms that list equities or commodities as perpetual contracts depend entirely on oracles to determine mark price and therefore liquidation levels. The oracle spec is often buried in documentation and rarely monitored by traders. When the denomination changes at a scheduled time, the oracle cannot make an adjustment and simply reads the new price, creating an instant apparent move of 30 to 50% or more.
- ## Core Concept
	- An oracle reads a price denominated in one currency. If at a fixed time the contract switches its reference to a price denominated in a stronger currency, the mark price rises by the ratio of the two currencies. Traders short the perp are liquidated at what appears to be a large upward move, while longs profit. The move is not arbitrageable back to spot instantly because the oracle is authoritative for settlement.
- ## Mechanics
	- Identify platforms that list equity or commodity perps and read their oracle documentation to find the denomination currency for each listed instrument.
	- Check whether any denomination currency changes are scheduled or whether contracts roll between different reference sources at fixed times.
	- For corporate events with known dates that affect oracle inputs (dividends, splits, index rebalances), check whether the perp platform's oracle accounts for these adjustments. If it does not, a dividend ex-date will cause the oracle to show a sudden drop equal to the dividend, creating a predictable short.
	- For denomination changes, go long the perp before the scheduled change time and close after the artificial jump.
	- Monitor Google Alerts or equivalent for all equities listed on the platform to catch dividend announcements, split announcements, and other corporate actions.
- ## Entry / Trigger
	- Confirmed scheduled denomination change or unaccounted corporate event on a perp whose oracle will reflect the raw price change without adjustment.
- ## Risk Management
	- The primary risk is that the platform identifies the anomaly before the event and patches the oracle or halts the market. Position size should reflect this binary outcome.
	- Timing precision matters because the jump occurs at a specific transition moment. Holding too long after the event reintroduces directional risk.
- ## Examples
	- A stock was trading at approximately $10 on a crypto perp platform. At a scheduled rollover time, the oracle switched denomination from USD to GBP. Because GBP/USD was approximately 0.75, the GBP-denominated price was roughly $13 to $14 in USD equivalent. Traders short the perp were liquidated by an approximately 40% upward move that reflected only the FX conversion, not any change in the company's value.
- ## Caveats & Edge Cases
	- This edge is highly time-sensitive and will close once platforms update their oracle handling or traders systematically monitor for it.
	- Not all platforms handle corporate actions the same way. Validate the oracle spec for each platform and each instrument independently before trading.
	- Liquidity on these perps is often thin, which limits scalable size and can cause slippage on entry and exit.
