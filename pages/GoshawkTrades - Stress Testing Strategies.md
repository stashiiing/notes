- author:: [[GoshawkTrades]]
  summary:: Stress testing deliberately subjects a strategy to worst-case scenarios and degraded execution conditions to assess its robustness. This includes testing across historical crises, inflating slippage and commissions, and introducing execution delays. A strategy that survives stress testing provides far greater confidence for live deployment than one tested only under normal conditions.
  category:: [[framework]], [[concept]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe::
  market:: [[all]]
  instrument::
  tools:: [[backtesting]], [[slippage modelling]], [[execution delay simulation]]
  difficulty:: [[intermediate]]
  source:: [https://www.youtube.com/watch?v=W722Ca8tS7g&t=376s] [6:16]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=W722Ca8tS7g&t=376s}}
- # Stress Testing Strategies
- ## TL;DR
	- Stress testing throws the worst conditions at your strategy: historical crises, inflated transaction costs, and execution delays. Most backtests look great because they assume normal markets and perfect execution. Strategies that survive degraded conditions are far more likely to perform when deployed with real capital, and they also give the trader greater psychological confidence.
- ### Context
	- Backtests typically assume ideal execution: minimal slippage, instant fills, and stable market conditions. In reality, markets experience flash crashes, liquidity crises, and infrastructure failures. A strategy that appears profitable under perfect conditions may collapse when any of these assumptions break down. Stress testing forces you to confront these scenarios before your capital is at risk.
- ## Core Concept
	- The idea is to intentionally degrade the conditions under which your strategy operates and observe how performance responds. If the strategy remains profitable (even at reduced levels), it demonstrates resilience. If it collapses entirely, the original results were likely dependent on assumptions that will not hold in live trading.
- ## Mechanics
	- Test the strategy across known crisis periods: the 2008 financial crisis, the March 2020 crash, and any relevant flash crashes for your market.
	- Double or triple the commission assumptions in your backtest to see if the strategy survives higher transaction costs.
	- Increase slippage from your baseline assumption (e.g., move from 0.01% to 0.1% or higher) and observe the impact on returns.
	- Introduce execution delays: shift the signal to execution time from instant to progressively longer intervals (e.g., 1 day, 3 days, 5 days).
	- For lower timeframe strategies, test delays measured in minutes rather than days (e.g., instant to 5 minutes).
	- Evaluate whether the strategy remains profitable or at least avoids catastrophic losses under each degraded condition.
- ## Examples
	- GoshawkTrades tested a crypto momentum strategy by shifting execution from day zero to day five. Day zero was not actually the peak performance point; a one day delay performed slightly better. This is a strong positive sign because it shows the signal persists over a meaningful time horizon, making the strategy resilient to real world execution imperfections.
	- Negative example: a lower timeframe strategy that becomes completely unprofitable when execution shifts from instant to five minutes later. This fragility is a warning sign because perfectly instant execution is rarely achievable at scale.
- ## Caveats & Edge Cases
	- Stress testing can give false comfort if the crisis scenarios tested do not represent the type of risk your strategy is actually exposed to. Always choose stress events that are relevant to your market and timeframe.
	- Execution delay testing is not supported on all backtesting platforms. You may need custom code to implement it properly.
	- A strategy that survives stress testing is not guaranteed to be profitable live; this test validates robustness, not edge strength. Combine it with the other three validation techniques.
