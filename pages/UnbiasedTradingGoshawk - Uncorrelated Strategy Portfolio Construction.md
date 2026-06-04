author:: [[GoshawkTrades]]
summary:: The central goal of algorithmic portfolio construction is to accumulate strategies whose returns are as uncorrelated as possible. This requires diversifying across instruments, strategy types and time frames. Diminishing returns set in above roughly 12–15 strategies, and the greatest diversification gains come from going from one strategy to five.
category:: [[framework]]
sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
timeframe::
market:: [[all]]
instrument::
tools:: [[correlation matrix]], [[volatility targeting]]
difficulty:: [[intermediate]]
source:: https://www.youtube.com/watch?v= [08:32]
status:: [[draft]]

- # Uncorrelated Strategy Portfolio Construction
- ## TL;DR
	- Build a portfolio of strategies that do not move together. Diversify across instruments, strategy types (trend, mean reversion, arb) and time frames. The biggest diversification gains come early — from one strategy to five. Above 10–12 strategies, new additions rarely add genuine diversification.
- ### Context
	- Minir runs nine active strategies after closing three that became correlated or redundant. He treats the portfolio as a business with multiple revenue streams, and evaluates every new strategy by asking whether it reduces overall correlation rather than whether it performs well in isolation.
- ## Core Concept
	- A single strategy, however good, concentrates all risk on one set of market conditions. Stacking genuinely uncorrelated strategies smooths the equity curve because losses in one regime are offset by gains in another. The instrument choice is often more powerful than the signal logic — soybeans and BTC are structurally uncorrelated even if both use the same trend-following signal.
- ## Mechanics
	- Identify what strategy types you currently run and map their correlations.
	- Add new strategies by asking: does this reduce correlation in my existing portfolio?
	- Prioritise different instruments over different signals — the same signal on uncorrelated assets gives real diversification.
	- Use a correlation matrix reviewed quarterly. If a strategy's correlation to others rises and sustains for a quarter or more, consider removing it.
	- Aim for roughly: trend following, mean reversion and a small allocation to opportunistic or arbitrage strategies.
	- Stop adding strategies once you reach roughly 10–12; above that, the marginal benefit is very small and maintenance cost rises.
	- Leave a portion of capital unallocated so you can deploy into short-lived inefficiencies when they arise.
- ## Caveats & Edge Cases
	- Instruments that look uncorrelated (Nasdaq, BTC) can become correlated during risk-off macro events. True uncorrelation requires genuine instrument diversity — commodities, crypto, equities, FX.
	- Claiming to run 50 strategies rarely reflects real diversification; most will cluster into a few correlated groups.
	- Correlation between strategies can change over time. A strategy that was uncorrelated for two years may become correlated — monitor continuously rather than assuming static relationships.