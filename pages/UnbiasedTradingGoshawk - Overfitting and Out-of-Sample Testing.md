- author:: [[UnbiasedTradingGoshawk]]
  summary:: The most common failure mode in algorithmic trading is overfitting: tuning too many parameters to historical data so the backtest looks perfect but live performance collapses. The solution is strict out-of-sample testing and keeping strategies to two or three free parameters maximum.
  category:: [[concept]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe::
  market:: [[all]]
  instrument::
  tools:: [[backtesting]], [[out-of-sample testing]], [[walk-forward]]
  difficulty:: [[intermediate]]
  source:: https://www.youtube.com/watch?v= [54:22]
  status:: [[draft]]
- # Overfitting and Out-of-Sample Testing
- ## TL;DR
	- Fitting too many parameters to historical data produces strategies that look great in backtests and fail immediately in live trading. Keep parameters to two or three, reserve two or more years of data as a true out-of-sample test set, and never optimise on that held-out data.
- ### Context
	- Minir cites this as the single most common mistake he sees from traders building algorithmic strategies. It is especially tempting to add filters and indicators to fix every losing trade in a backtest, but each addition reduces robustness.
- ## Core Concept
	- Every parameter added to a strategy is a degree of freedom being fitted to noise in historical data. A strategy with ten parameters will find spurious patterns that vanish on new data. Treating historical data as a finite resource — splitting it strictly into in-sample (development) and out-of-sample (validation) sets — forces an honest assessment of whether the edge is real.
- ## Mechanics
	- Limit strategy parameters to two or three. Think of each parameter as a tuning knob: eliminate as many as possible.
	- Split your historical data: use roughly two to three years for development and optimisation, and reserve a separate two-year block as the out-of-sample test. Never touch the out-of-sample data during development.
	- After finalising the strategy on in-sample data, run it once on the out-of-sample set. Do not iterate further after seeing out-of-sample results.
	- Expect the out-of-sample to underperform in-sample. If performance is within a reasonable margin — not drastically worse — the strategy is a candidate for live deployment.
	- Live trading is itself an ongoing out-of-sample test. Monitor whether live results track the out-of-sample expectation.
- ## Caveats & Edge Cases
	- Machine learning models amplify overfitting risk because they can fit thousands of implicit parameters. Use them with extra caution and larger out-of-sample sets.
	- A strategy can pass out-of-sample testing and still fail live if market regime has changed. Out-of-sample testing reduces but does not eliminate this risk.
	- Adding filters to fix individual losing trades is the most common path to overfitting. If a loss was valid given the rules, accept it rather than patch the strategy.
