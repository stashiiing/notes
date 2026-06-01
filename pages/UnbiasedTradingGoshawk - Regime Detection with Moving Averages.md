- author:: [[UnbiasedTradingGoshawk]]
  summary:: A simple moving average-based regime filter to switch between trend-following and mean-reversion modes. Price above the 200 MA or 50 MA signals a trending regime; price between the two signals chop. This prevents taking mean-reversion trades in a strong trend and vice versa.
  category:: [[concept]]
  sub-cat:: [[systematic]], [[algorithmic]], [[price-action]]
  timeframe:: [[swing]], [[position]]
  market:: [[all]]
  instrument::
  tools:: [[moving average]], [[200 MA]], [[50 MA]], [[regime filter]]
  difficulty:: [[beginner]]
  source:: https://www.youtube.com/watch?v= [25:56]
  status:: [[draft]]
- # Regime Detection with Moving Averages
- ## TL;DR
	- Use the 50 and 200 MA as a simple regime filter. Above the 200 MA tends to be trending; between the two tends to be choppy. Disable mean-reversion entries in trending regimes and vice versa. No filter is perfect, but running trend and mean-reversion strategies simultaneously provides a natural hedge when the regime detection is imprecise.
- ### Context
	- Minir tried for years to find a reliable indicator that definitively signals trending versus choppy conditions. He found none. The 50/200 MA approach is not a perfect classifier but it is robust, simple and avoids the overfitting risk that comes with more complex regime models.
- ## Core Concept
	- Markets oscillate between trending and mean-reverting regimes. A mean-reversion strategy applied during a strong trend, or a trend strategy applied during chop, will lose money. A simple moving average relationship provides a lagging but robust proxy for the current regime. Running both strategy types simultaneously and filtering each by regime reduces drawdown without requiring a perfect classifier.
- ## Mechanics
	- Plot the 50-period and 200-period moving averages on the relevant time frame (daily is most common).
	- If price is above the 200 MA: classify as trending. Favour trend-following signals; suppress mean-reversion entries.
	- If price is between the 50 MA and 200 MA: classify as choppy or transitional. Favour mean-reversion signals; suppress or reduce trend entries.
	- If price is below the 200 MA: classify as downtrend. Trend-following to the short side is valid; mean reversion longs should be suppressed.
	- Run trend and mean-reversion strategies simultaneously. Even when the regime filter is wrong, the other strategy type partially offsets the losses.
- ## Caveats & Edge Cases
	- Moving averages are lagging. A regime change will not be detected until the MA relationship has already shifted, meaning some drawdown is unavoidable at transitions.
	- No single indicator reliably identifies trend versus chop in real time. The value of this approach is simplicity and robustness, not precision.
	- Applying the same MA lengths across all instruments is unlikely to be optimal. The 50/200 pair is a reasonable starting point rather than a universal truth.
