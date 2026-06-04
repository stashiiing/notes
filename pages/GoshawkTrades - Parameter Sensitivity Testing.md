- author:: [[GoshawkTrades]]
  summary:: Parameter sensitivity testing reveals whether a trading strategy has a genuine edge or is merely curve-fitted to historical noise. By varying input parameters slightly and observing how performance responds, traders can identify overfitting before deploying capital. Robust strategies show smooth, gradual performance changes across parameter ranges rather than sharp cliffs.
  category:: [[concept]], [[framework]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe::
  market:: [[all]]
  instrument::
  tools:: [[heatmaps]], [[backtesting]], [[parameter optimisation]]
  difficulty:: [[intermediate]]
  source:: [https://www.youtube.com/watch?v=W722Ca8tS7g&t=47s] [0:47]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=W722Ca8tS7g&t=47s}}
- # Parameter Sensitivity Testing
- ## TL;DR
	- Parameter sensitivity testing checks how small changes in strategy inputs affect performance. If shifting a moving average period from 20 to 22 destroys your returns, the strategy is almost certainly overfit. Robust strategies maintain relatively stable performance across a range of nearby parameter values, degrading gradually rather than collapsing at a single "magic number."
- ### Context
	- Most traders optimise a strategy to find the single best parameter combination, then assume those results will persist in live markets. This approach is dangerous because markets evolve, and a strategy that only works at one exact setting has no real edge. Parameter sensitivity testing, used by firms like Renaissance Technologies and Susquehanna, provides a straightforward way to distinguish genuine alpha from statistical noise before risking real capital.
- ## Core Concept
	- The test works by systematically varying one or more strategy parameters across a range and measuring how performance changes. A genuine edge will produce a "plateau" of profitability around the optimal value, with returns declining smoothly as parameters move away from the centre. An overfit strategy, by contrast, will show erratic spikes where a single setting produces exceptional returns but neighbouring values produce losses.
- ## Mechanics
	- Select the key parameters in your strategy (e.g., moving average length, RSI period, lookback window).
	- Define a reasonable range for each parameter (e.g., RSI 10 through 20 in increments of 1).
	- Run the backtest for every combination of parameter values across that range.
	- Visualise the results using a heatmap or surface plot. One axis represents one parameter, the other axis represents a second parameter, and colour intensity represents profitability.
	- Look for a broad, warm coloured cluster around the optimal zone. Returns should degrade gradually toward the edges rather than dropping off a cliff.
	- If performance spikes at one isolated value and collapses at neighbours, flag the strategy as likely overfit.
- ## Examples
	- RSI strategy (overfit): RSI 14 returns 50%, RSI 15 returns minus 10%, RSI 16 returns 5%. There is no cohesion between adjacent values, suggesting the strategy is fitting to noise.
	- RSI strategy (robust): RSI 12 returns 18%, RSI 14 returns 22%, RSI 16 returns 20%, RSI 18 returns 17%. The values do not match exactly, but they remain in a consistent range, indicating a genuine underlying edge.
- ## Caveats & Edge Cases
	- This test does not guarantee live profitability on its own; it should be combined with the other validation techniques (walk-forward, stress testing, Monte Carlo).
	- Very wide parameter ranges can sometimes mask local overfitting. Focus on the neighbourhood around your chosen parameter, not just the full spectrum.
	- Some strategies have inherently sensitive parameters (e.g., mean reversion thresholds in illiquid markets). Context matters when interpreting results.
