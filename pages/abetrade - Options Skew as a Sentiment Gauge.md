- author:: [[abetrade]]
  summary:: The 25-delta risk reversal measures the difference in implied volatility between out-of-the-money calls and puts on the same underlying. A positive reading means the market is paying up for upside exposure; a negative reading means it is paying up for downside protection. In crypto, the edge has historically been in fading the extremes: when everyone is crammed into calls, upside is already priced; when everyone is buying puts, fear is already in. Liquid options data is currently only available for Bitcoin and ETH via Deribit.
  category:: [[concept]], [[framework]]
  sub-cat:: [[orderflow]], [[quantitative]]
  timeframe:: [[swing]], [[position]]
  market:: [[crypto]]
  instrument:: [[options]]
  tools:: [[options skew]], [[implied volatility]]
  difficulty:: [[advanced]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Options Skew as a Sentiment Gauge
- ## TL;DR
	- The 25-delta risk reversal is the gap in implied volatility between a 25-delta call and a 25-delta put. When calls are bid up relative to puts, the market is paying up for upside. When puts are bid, the market is paying up for protection. A trader does not need to trade options to use this signal; it is one of the cleanest real-time reads on market sentiment available. In crypto, the edge has been in fading the extremes in both directions. Currently only meaningful for Bitcoin and ETH due to liquidity constraints.
- ### Context
	- Options markets reveal what participants are willing to pay for asymmetric exposure in a way that spot or perp markets do not. The skew adds a third sentiment dimension alongside open interest and funding, completing the positioning picture. It is particularly useful when it confirms or contradicts what the derivatives data is showing.
- ## Core Concept
	- Implied volatility (IV) is the market's forward estimate of how much an asset will move, embedded in an option's price. Delta measures how much the option price moves per one dollar move in the underlying (0 to 1 for calls, 0 to -1 for puts). A 25-delta option sits moderately out of the money: far enough to reflect real positioning, close enough to stay liquid.

	  25-delta Risk Reversal = IV(25-delta Call) minus IV(25-delta Put)

	  When calls trade at a higher implied volatility than puts of the same delta, the risk reversal is positive: the market is paying a premium for upside exposure. When puts are richer, the risk reversal is negative: the market is paying up for downside protection.

	  At extremes in either direction, the sentiment is already priced and the reward for chasing in the same direction is thin. Fading the extreme means leaning against crowded positioning before it reverses.
- ## Mechanics
	- Monitor the 25-delta risk reversal on Deribit for BTC and ETH. This is the most liquid options market in crypto and the reference for skew data.
	- A strongly positive risk reversal alongside elevated open interest and high positive funding is a convergence of froth signals across all three data types.
	- A deeply negative risk reversal alongside depressed open interest and negative funding is the convergence of fear signals.
	- Z-score the risk reversal over a rolling window to judge whether the current reading is statistically extreme for that asset.
	- Fading signal: extremes in either direction have historically been closer to reversal than continuation.
- ## Caveats & Edge Cases
	- Liquid options only exist for BTC and ETH in crypto currently. Other markets do not have enough options volume to generate meaningful skew data.
	- Options skew is a sentiment indicator, not a precise timing tool. An extreme can persist or become more extreme before reversing.
	- The signal is most powerful when it confirms what the open interest and funding data are already showing, and least reliable in isolation.
	- Bitcoin options are now more contested between Deribit and CME/ETF-linked products following the growth of listed products through 2025. Deribit remains the reference for the skew data that matters here.
