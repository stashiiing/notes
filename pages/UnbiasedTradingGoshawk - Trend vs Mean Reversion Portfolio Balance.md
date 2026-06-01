- author:: [[UnbiasedTradingGoshawk]]
  summary:: Minir allocates roughly 40% of his portfolio to trend-following strategies, 35% to mean reversion and the remainder to opportunistic or arbitrage plays. Trend following generates the majority of returns but produces deep drawdowns in choppy markets; mean reversion acts as a partial hedge during those periods.
  category:: [[framework]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe::
  market:: [[all]]
  instrument::
  tools:: [[portfolio allocation]], [[trend following]], [[mean reversion]]
  difficulty:: [[intermediate]]
  source:: https://www.youtube.com/watch?v= [26:40]
  status:: [[draft]]
- # Trend vs Mean Reversion Portfolio Balance
- ## TL;DR
	- Hold roughly 40% in trend strategies and 35% in mean-reversion strategies. Trend generates the bulk of returns when markets move directionally; mean reversion cushions equity curve drawdowns during choppy conditions. The two strategy types are naturally partially offsetting, which smooths performance without needing perfect regime detection.
- ### Context
	- Minir acknowledges he is always slightly more trend-heavy than he wants to be, simply because trend following has the strongest long-run return profile across markets. Mean reversion is treated as an insurance position rather than a primary return driver.
- ## Core Concept
	- Trend strategies excel when prices move persistently in one direction. Mean-reversion strategies excel when prices oscillate around a central value. Because these conditions alternate unpredictably, holding both simultaneously reduces the periods of flat or negative performance. The allocation is not about optimising for maximum return but for a smoother, more sustainable equity curve.
- ## Mechanics
	- Target approximately 40% of risk capital allocated to trend-following strategies across multiple instruments and time frames.
	- Target approximately 35% allocated to mean-reversion strategies, ideally on instruments or time frames with low correlation to the trend book.
	- Reserve the remaining roughly 25% for opportunistic strategies: arbitrage, short-lived inefficiencies and discretionary bets.
	- Review allocations when correlation between the trend and mean-reversion books rises significantly — that signals regime stress and may require rebalancing.
- ## Caveats & Edge Cases
	- The specific percentages (40/35/25) are Minir's own portfolio and reflect his instrument mix, risk tolerance and available strategies. They are illustrative rather than prescriptive.
	- Mean-reversion strategies are harder to find that generate 100–200% annual returns. Their primary value is drawdown reduction, not return maximisation.
	- In strongly trending markets the mean-reversion book will drag performance. Accept this as the cost of a smoother equity curve.
