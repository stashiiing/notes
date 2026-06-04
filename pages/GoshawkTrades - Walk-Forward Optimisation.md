- author:: [[GoshawkTrades]]
  summary:: Walk-forward optimisation splits historical data into rolling training and testing windows to validate whether a strategy generalises beyond its optimisation period. It prevents the common mistake of optimising over all available data and then being surprised when the strategy fails live. Consistency between in-sample and out-of-sample performance is the key signal.
  category:: [[framework]], [[concept]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe::
  market:: [[all]]
  instrument::
  tools:: [[backtesting]], [[walk-forward analysis]], [[out-of-sample testing]]
  difficulty:: [[intermediate]]
  source:: [https://www.youtube.com/watch?v=W722Ca8tS7g&t=263s] [4:23]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=W722Ca8tS7g&t=263s}}
- # Walk-Forward Optimisation
- ## TL;DR
	- Walk-forward optimisation divides your data into sequential training and testing windows that roll forward through time, ensuring your strategy is always evaluated on data it has never seen. If the strategy cannot perform on out-of-sample data, it is unlikely to work live. This technique is one of the most effective defences against overfitting.
- ### Context
	- Most traders optimise a strategy across their entire dataset, find parameters that look excellent historically, and then deploy them live. The problem is that with enough parameter combinations, something will always appear to work on any given dataset. Walk-forward optimisation solves this by ensuring the strategy must prove itself repeatedly on unseen data, mimicking how it would actually encounter new market conditions in real time.
- ## Core Concept
	- The method works by splitting the historical data into a training (in-sample) window and a testing (out-of-sample) window. The strategy is optimised on the training window, then evaluated on the testing window without any further adjustments. The entire process then shifts forward in time and repeats. If the strategy consistently performs on the out-of-sample segments, it suggests a genuine edge rather than memorised patterns.
- ## Mechanics
	- Choose a training window length (e.g., 1 year) and a testing window length (e.g., 6 months).
	- Optimise your strategy parameters on the first training window.
	- Apply those optimised parameters to the immediately following testing window and record performance.
	- Slide both windows forward by the length of the testing window and repeat.
	- Continue until you have exhausted all available data.
	- Compare the average performance across all out-of-sample windows to the in-sample results.
	- Expect out-of-sample performance to be somewhat lower than in-sample; this is normal. What matters is that it remains positive and directionally consistent.
- ## Examples
	- Healthy result: In-sample averages 20% per year, out-of-sample averages 7 to 8% per year. The drop is expected because no optimisation was performed on the testing data, but the strategy still generates positive returns.
	- Unhealthy result: In-sample averages 20% per year, out-of-sample averages minus 10% per year. This large divergence indicates the strategy has memorised historical patterns rather than capturing a real edge.
- ## Caveats & Edge Cases
	- The ratio of training to testing window length matters. Too short a training window may not capture enough market regimes; too long may make the optimisation stale by the time it reaches the test period.
	- Walk-forward does not eliminate all overfitting risk. It should be used alongside parameter sensitivity, stress testing, and Monte Carlo simulations for a complete validation framework.
	- Some strategies with very few trades per year may not generate enough data in each out-of-sample window to draw reliable conclusions.
