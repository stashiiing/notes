- author:: [[abetrade]]
  summary:: A z-score converts any raw derivatives metric into a standardised measure of how extreme the current reading is relative to the asset's own recent history. This makes open interest, funding, liquidations, order book skew, and options skew all comparable on one scale across coins of wildly different sizes. Readings above +2 or below -2 standard deviations mark statistically unusual positioning extremes and are the basis for screening the market for high-conviction setups without manually reviewing hundreds of charts.
  category:: [[framework]]
  sub-cat:: [[quantitative]], [[systematic]]
  timeframe::
  market:: [[crypto]]
  instrument::
  tools:: [[open interest]], [[funding rate]], [[liquidations]]
  difficulty:: [[intermediate]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Z-Score Standardisation for Trading Signals
- ## TL;DR
	- The raw number for any derivatives metric is hard to judge in isolation. Is a 50 million dollar jump in open interest big? Is funding at minus 0.05% extreme? The answer depends entirely on the coin and on what is normal for that coin. The z-score solves this by measuring how far the current reading sits from the asset's own recent average in units of standard deviation. A +2 on PENGU open interest and a +2 on Bitcoin open interest mean the same thing (two standard deviations above recent normal), even though the raw dollar figures are worlds apart. This makes every metric comparable across all coins on one scale.
- ### Context
	- Screening hundreds of coins manually for stretched derivatives positioning is impractical without a standardised measure. The z-score is the tool that converts diverse raw metrics into a single comparable scale, enabling systematic scanning for statistically unusual setups and the ranking of the entire market by extremity of positioning.
- ## Core Concept
	- Z-Score = (Current Value minus Average) / Standard Deviation

	  A z-score of 0 is an average reading. A z-score of +2 is two standard deviations above average, which on a normal distribution is roughly the top 2.5% of all readings. A z-score of -2 is the equivalent extreme on the downside. The larger the absolute value, the more unusual the current positioning relative to that coin's own history.

	  The score is calculated over a rolling window (e.g., 30 days), so it always judges the current reading against the coin's recent behaviour rather than its entire history. This keeps the measure relevant as a market's character changes over time.

	  Applied to open interest, funding, liquidations, spot book skew, and options risk reversals, the z-score converts five different metrics with five different units and scales into one number each that can be directly compared and ranked.
- ## Mechanics
	- Define the rolling lookback window (30 days is a common choice). Compute the rolling mean and rolling standard deviation of the metric over that window.
	- Z-Score = (Today's reading minus rolling mean) / rolling standard deviation.
	- Readings above +2 or below -2 flag statistically unusual positioning that warrants closer attention.
	- Rankings: sort the entire universe of coins by z-score on a given metric each day to identify the handful where positioning is genuinely stretched, rather than manually reviewing every chart.
	- Combine z-scores across metrics. A coin showing +2 or above on open interest and a strongly positive funding z-score simultaneously is a higher-conviction froth signal than either alone.
	- A percentile rank alongside the z-score provides an additional reference: a 98th percentile reading means the current value is higher than 98% of all readings in the lookback window.
- ## Examples
	- PENGU: The open interest z-score flagged the setup before the rally ran. Screening for statistically extreme open interest with muted funding identified the trade opportunity systematically rather than through chart browsing.
- ## Caveats & Edge Cases
	- A 30-day lookback may be too short for slow-moving or newly listed assets and too long for fast-moving markets. The appropriate window depends on the asset's typical volatility and cycle length.
	- Z-scores assume the underlying distribution is roughly normal. Derivatives metrics in crypto can have fat tails and are not strictly normal, so extreme z-scores can persist longer than a normal distribution would suggest.
	- The z-score is a relative measure. A +2 during a period of generally low open interest is a different signal from a +2 during a period of generally elevated open interest. Context and the raw level still matter.
