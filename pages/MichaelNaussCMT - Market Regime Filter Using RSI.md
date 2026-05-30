- author:: [[MichaelNaussCMT]]
  summary:: A binary market regime gate that uses the four-period RSI of the S&P 500 to determine whether conditions are favourable for deploying a mean-reversion strategy. When the RSI(4) is above 50 the system is active and positions are held; when it falls to 50 or below all positions are exited and capital moves to cash until the regime recovers.
  category:: [[concept]]
  sub-cat:: [[systematic]], [[quantitative]]
  timeframe:: [[position]]
  market:: [[equities]]
  instrument:: [[spot]]
  tools:: [[RSI]], [[S&P-500]]
  difficulty:: [[beginner]]
  source:: https://letters.statsedgetrading.com
  status:: [[draft]]
- # Market Regime Filter Using RSI
- ## TL;DR
	- A simple, rules-based switch that gates a strategy on or off depending on the short-term momentum of a broad market index. The S&P 500 four-period RSI above 50 signals a healthy regime where mean-reversion strategies have positive expectancy. A reading at or below 50 signals a deteriorating regime; the system exits all positions and sits in cash. The filter prevents the common failure mode of catching falling knives during genuine bear markets.
- ### Context
	- Mean reversion inside an uptrend is a well-documented edge in healthy markets. The same strategy applied indiscriminately across all market conditions produces significantly worse results because, during bear markets, short-term dips tend to extend rather than recover. The regime filter solves this by switching off deployment entirely when broad market conditions are unfavourable, accepting periods in cash as the cost of avoiding the worst drawdown environments.
- ## Core Concept
	- Use the four-period RSI of the S&P 500 as a binary gate. A reading above 50 defines a healthy regime; below or equal to 50 defines an unhealthy regime. The strategy only operates during healthy regimes. This is not a predictive signal; it is a contemporaneous condition check that keeps the system aligned with the market environment in which its edge has historically existed.
- ## Mechanics
	- At each rebalance (monthly for the Starter System), check whether the S&P 500 RSI(4) is greater than 50.
	- If true, proceed with normal screening and position entry.
	- If false, open no new positions. Any positions currently held are closed immediately.
	- Capital remains in cash until the next rebalance at which the condition is again true.
	- The same check also applies mid-month as an intra-period exit trigger: if the S&P 500 RSI(4) falls to 50 or below between scheduled rebalances, existing positions are exited without waiting for month-end.
	- The result is that the system is invested approximately 73.9% of the time, with roughly 26% of the time held in cash during bearish periods.
- ## Caveats & Edge Cases
	- The filter uses a very short lookback (four periods) and therefore reacts quickly; this reduces exposure during fast deteriorations but can also cause brief periods in cash during shallow corrections that recover quickly. The threshold of 50 is specific to this implementation and should be validated rather than assumed to be universally optimal. The filter addresses broad market risk only; individual stock deterioration is handled separately by the price-versus-moving-average stop on each position. Running a mean-reversion strategy without any regime filter, or with a filter set too loosely, substantially worsens drawdown characteristics.
