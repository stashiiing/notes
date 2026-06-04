- author:: [[GoshawkTrades]]
  summary:: Monte Carlo simulations randomise the sequence of historical trades thousands of times to reveal the true range of possible outcomes a strategy could produce. Because a single backtest represents only one path through history, reshuffling trade order exposes the realistic range of drawdowns and returns. This information is critical for setting appropriate position sizes and managing psychological expectations.
  category:: [[concept]], [[framework]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe::
  market:: [[all]]
  instrument::
  tools:: [[backtesting]], [[Monte Carlo simulation]], [[position sizing]]
  difficulty:: [[advanced]]
  source:: [https://www.youtube.com/watch?v=W722Ca8tS7g&t=532s] [8:52]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=W722Ca8tS7g&t=532s}}
- # Monte Carlo Simulations
- ## TL;DR
	- Monte Carlo simulations take your historical trades and reshuffle them into thousands of different sequences, producing thousands of possible equity curves from the same set of trades. This reveals the true risk range of your strategy, including worst-case drawdowns that your single backtest may have hidden. The results are essential for calibrating position sizing and setting realistic expectations before going live.
- ### Context
	- A standard backtest shows one specific ordering of trades and the equity curve that resulted. Traders often anchor to this single path, assuming their live experience will resemble it. In reality, the same trades could have occurred in any order, and some orderings would have produced dramatically worse drawdowns. Monte Carlo simulations provide a reality check by showing the full distribution of possible outcomes.
- ## Core Concept
	- The simulation takes all of the trades from a backtest and randomly reorders them thousands of times. Each reshuffled sequence generates a new equity curve. The collection of all these curves reveals the probability distribution of returns and drawdowns the strategy could realistically produce. The key insight is that your backtest is just one sample from this distribution, not the expected outcome.
- ## Mechanics
	- Collect the full list of trades (with their individual profit and loss values) from a completed backtest.
	- Randomly reshuffle the order of those trades to create a new sequence.
	- Calculate the equity curve for this reshuffled sequence.
	- Repeat the reshuffling process thousands of times (typically 1,000 to 10,000 iterations).
	- Plot all resulting equity curves together to visualise the distribution.
	- Identify the median outcome, the best case outcomes, and critically the worst case outcomes.
	- Use the worst case curves to stress test your position sizing: ask whether your account could survive the maximum drawdown observed across all simulations.
- ## Risk Management
	- If the worst case Monte Carlo paths show drawdowns that would blow up your account or cause you to abandon the strategy psychologically, reduce your position sizes until the worst case is survivable.
	- The simulation output directly informs how aggressively you can size a given strategy. A wide dispersion of outcomes suggests conservative sizing; a narrow band allows more aggression.
	- If a significant number of simulated paths (e.g., 10 out of 1,000) go straight to zero or near zero, it indicates the strategy is sized far too aggressively regardless of how the average path looks.
- ## Examples
	- A Monte Carlo simulation of 100 historical trades produces 1,000 equity curves. Most curve upward steadily, but roughly 10 paths show severe drawdowns far beyond what the original backtest displayed. This tells the trader that while the strategy has a positive edge, an unlucky trade sequence could produce a much deeper drawdown than the single backtest suggested. The appropriate response is to reduce position sizes until even those worst case paths remain survivable.
- ## Caveats & Edge Cases
	- Standard Monte Carlo assumes trades are independent of each other. If your strategy has sequential dependencies (e.g., it performs differently after a winning streak), simple reshuffling may not fully capture the risk.
	- The simulation does not generate new trades or test new market conditions. It only reorders existing trades, so it cannot account for regime changes or black swan events not present in the original data.
	- Monte Carlo is a complement to, not a replacement for, the other three validation techniques. A strategy should pass parameter sensitivity, walk-forward optimisation, and stress testing before Monte Carlo is used to calibrate sizing.
