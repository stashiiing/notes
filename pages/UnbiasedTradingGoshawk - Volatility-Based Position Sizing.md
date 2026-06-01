- author:: [[UnbiasedTradingGoshawk]]
  summary:: Size positions by targeting a consistent volatility contribution per trade rather than targeting a fixed return. Higher-volatility assets receive smaller allocations; lower-volatility assets receive larger ones. This keeps risk normalised across instruments and strategies.
  category:: [[framework]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe::
  market:: [[all]]
  instrument::
  tools:: [[volatility targeting]], [[ATR]], [[position sizing]]
  difficulty:: [[intermediate]]
  source:: https://www.youtube.com/watch?v= [40:38]
  status:: [[draft]]
- # Volatility-Based Position Sizing
- ## TL;DR
	- Do not size positions to hit a return target. Size them to contribute a consistent, controlled amount of volatility to the portfolio. This is the only variable you can reliably control. Returns follow from having good signals and letting this sizing framework compound over time.
- ### Context
	- Minir applies volatility sizing at two levels: per trade (based on the current volatility of the instrument) and per strategy (each strategy's allocation within the portfolio is also volatility-adjusted). He notes that more complex sizing methods exist but that the marginal gain from complexity is rarely worth it at sub-institutional capital sizes.
- ## Core Concept
	- You cannot control returns. You can control how much risk each position takes. By normalising all positions to a consistent volatility target, you prevent any single high-volatility instrument from dominating the portfolio's P&L swings. A volatile instrument like crude oil gets a smaller notional position than a calmer one, so both contribute roughly equally to portfolio risk.
- ## Mechanics
	- Measure recent volatility for each instrument (e.g. ATR or rolling standard deviation of returns over 20 days).
	- Determine the target risk per trade as a percentage of portfolio equity.
	- Position size = (target risk amount) / (instrument volatility in dollar terms).
	- Repeat at the strategy level: allocate capital across strategies proportionally to their inverse volatility so that no single strategy dominates in volatile periods.
	- Review sizing periodically — instrument volatility regimes change.
- ## Caveats & Edge Cases
	- Volatility sizing does not protect against gap risk or halt risk where realised loss exceeds the modelled volatility.
	- During correlated market stress, all positions may move adversely simultaneously even if individually sized correctly. Portfolio-level correlation management is a complement to, not a substitute for, per-position sizing.
	- At very small account sizes, the maths may produce position sizes too small to execute (fractional contracts). Round sensibly and accept the approximation.
