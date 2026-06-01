- author:: [[UnbiasedTradingGoshawk]]
  summary:: A systematic short strategy targeting sub-500M market cap stocks gapping up significantly on news. Approximately 70% of gappers close red on the day, providing a repeatable edge. The primary challenge is risk management around halts and extreme intraday volatility near the open.
  category:: [[strategy]]
  sub-cat:: [[systematic]], [[algorithmic]]
  timeframe:: [[intraday]]
  market:: [[equities]]
  instrument:: [[spot]]
  tools:: [[gap scanner]], [[short selling]], [[risk management]]
  difficulty:: [[intermediate]]
  source:: https://www.youtube.com/watch?v= [04:19]
  status:: [[draft]]
- # Small Cap Gap-and-Fade Short Strategy
- ## TL;DR
	- Short sub-500M market cap stocks that gap up large on questionable news. Roughly 70% of these gappers close red on the day. The edge is statistical and repeatable; the main risk is halt exposure and extreme open volatility.
- ### Context
	- Minir discovered this edge by pulling historical small-cap data and observing the high close-red rate. It was his first profitable systematic strategy and compounded his account significantly in the first two years. The strategy is now more crowded but he considers it still viable with adaptation, attributing around 10% of his current portfolio to small-cap strategies.
- ## Core Concept
	- Sub-500M market cap stocks frequently gap up on fabricated or recycled news — companies claiming to have cured cancer, or repeating a prior press release to pump the stock for insider distribution. Because the catalyst is usually fake or overhyped, the stock reverts by end of day the majority of the time. Shorting the gap and holding through the day captures this mean-reversion premium.
- ## Mechanics
	- Filter for tickers: sub-500M or sub-1B market cap, gapping up significantly (20%, 50%, 100%+) on news.
	- Enter short after initial open volatility settles — do not short the exact open.
	- Hold through the day targeting a close near the prior day's price.
	- Size conservatively to survive extreme intraday spikes of 10–20% before the reversion.
	- Avoid holding through a halt. If a halt occurs, assess whether to hold or exit at reopening.
- ## Entry / Trigger
	- Large pre-market gap up on questionable or recycled news on a small-cap ticker. Confirm with a scanner filtering by market cap and gap percentage.
- ## Risk Management
	- The biggest risk is a regulatory halt — the exchange can freeze a ticker for days if fraud or news discrepancy is suspected, leaving a short position locked with no exit and ongoing locate fees.
	- Size positions so that a 20–30% adverse move does not cause catastrophic loss.
	- Accept that roughly 30% of trades will be losers; the edge is in the aggregate frequency of close-red outcomes.
	- Once account size reaches six figures and above, reassess: halt risk becomes asymmetrically dangerous relative to the edge. Consider reducing allocation or tightening filters.
- ## Examples
	- Minir compounded his early account significantly using this strategy from roughly 2020 onward.
	- He described being stuck in a halted ticker for four days, unable to exit, paying locates daily, with no certainty on whether the stock would reopen 500% higher or go to zero.
- ## Caveats & Edge Cases
	- The strategy has become more crowded since 2020. Adaptation is required — parameters and filters need periodic review.
	- During BTC bull runs, the crypto analogue (shorting new meme coin listings) can whipsaw badly, illustrating the same regime-sensitivity in a crypto context.
	- Not suited for large accounts without strict halt-risk controls.
	- Halts are fundamentally uncontrollable; position sizing is the only real defence.
