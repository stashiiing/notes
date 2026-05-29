author:: [[dlawant]]
summary:: A systematic covered call overlay on BTC can generate reliable positive yield across a wide range of market environments, but only within a specific parameter corridor (10-25 delta, 21+ day expiry) and only when a market regime filter is active. Three distinct implementation profiles emerge from the data corresponding to consistency, balanced yield, and yield-maximization mandates.
category:: [[strategy]], [[framework]]
sub-cat:: [[systematic]], [[quantitative]], [[earn]]
timeframe:: [[position]], [[investing]]
market:: [[crypto]]
instrument:: [[options]], [[spot]]
tools:: [[covered call]], [[delta]], [[implied volatility]], [[Deribit]], [[Black-76]], [[volatility risk premium]], [[regime filter]]
difficulty:: [[advanced]]
source:: [https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing](https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing)
status:: [[draft]]

- # Systematic BTC Covered Call Writing
- ## TL;DR
	- A covered call overlay on a long BTC position -- selling out-of-the-money calls at a target delta and collecting the premium -- can generate synthetic yield from Bitcoin's structural volatility risk premium. The strategy works reliably only within a specific parameter corridor (10-25 delta, 21+ day expiry) and only when a regime filter prevents selling into BTC's parabolic bull markets. Without those constraints, the strategy is a textbook "pennies in front of a steamroller" trade: many small wins periodically erased by catastrophic losses in trending environments.
- ### Context
	- BTC holders seeking yield have few native options. Covered call writing offers a way to harvest BTC's persistently elevated implied volatility without introducing counterparty risk or lending risk. The strategy has attracted growing institutional attention as the BTC options market has deepened and become accessible to traditional capital pools, but most retail and early institutional implementations have failed to capture the premium reliably because they ignored regime and parameter discipline.
- ## Core Concept
	- The strategy sells OTM calls on an existing BTC position at a chosen delta and expiry, collecting an upfront premium. If BTC stays below the strike, the full premium is kept. If BTC rallies through the strike, the collected premium is partially or fully offset by the cost of buying back the position. The net yield over many cycles should be positive if implied volatility consistently exceeds realized volatility -- which it has in BTC -- but only when the strategy avoids selling into the strong uptrends where that relationship breaks down most violently.
	- The strategy is classified as active management, not a passive overlay, because regime identification and exit discipline determine most of the outcome.
- ## Mechanics
	- **Parameter corridor:** Delta between 10 and 25, expiry 21 days or longer. Below 10-delta, yields are real but too thin for most institutional mandates. Above 25-delta, directional exposure from BTC bull runs overwhelms even a well-designed regime filter. Short-dated options (7 and 14 days) are structurally disadvantaged on BTC because the premium is too thin to absorb stop-loss events from BTC's intraday volatility.
	- **Option pricing:** Black-76 model, risk-free rate set to zero, strikes solved analytically from target delta. One volatility point of symmetric slippage applied on both entry and exit legs to simulate realistic execution (not mid-market fills).
	- **Execution cadence:** Entry, exit, and stop-loss checks run at hourly granularity. Performance metrics computed on daily-aggregated returns.
	- **Return convention:** Yields expressed as simple returns on initial capital, making the overlay yield directly additive to the BTC spot return.
	- **Regime filter (entry):** Two conditions must both be met. First, BTC's 10-day SMA must sit below its 30-day SMA, and the 30-day SMA must sit below the 50-day SMA (the strategy waits when shorter averages are stacked above longer ones, a classic bull trend). Second, the current 30-day implied volatility at the strategy delta must exceed its trailing 90-day rolling average (IV richness condition).
	- **Exit rules (three concurrent):** (1) Take-profit: close when the option has decayed to 25% of entry value (75% decay captured). (2) Delta stop-loss: exit if live delta rises above 0.45, enforcing a hard cap on directional exposure. (3) Time stop: close any position within 48 hours of expiry to avoid peak gamma risk.
	- **Re-entry:** Immediate re-entry after each exit when both entry conditions are satisfied. No cooling-off period.
- ## Entry / Trigger
	- Both regime filter conditions must be simultaneously true:
		- SMA stack is bearish or flat (10-day SMA below 30-day SMA, 30-day SMA below 50-day SMA)
		- Current 30-day IV at strategy delta is above its trailing 90-day rolling average
- ## Risk Management
	- **Delta stop-loss:** Exit immediately if the short call's live delta rises above 0.45. This is the primary defense against being run over in a trending market.
	- **Time stop:** Close all open positions within 48 hours of expiry. The final days before expiry carry maximum gamma risk; small spot moves cause large option value changes.
	- **Take-profit:** Close at 75% premium decay. Avoids holding through the period of declining theta-to-gamma ratio near expiry.
	- **Regime filter as position filter:** The most important risk control is not entering in the first place during strongly bullish regimes. The filtered strategy was in the market only 44% of the time over the 4.5-year study period.
	- **Sizing:** Held constant throughout the backtests at one unit per cycle. Active managers can improve outcomes materially by scaling position size with the strength of the regime and IV signals.
- ## Examples
	- **Recent 12-month window (Apr 2025 - Apr 2026):** A simple unfiltered 20-delta, 30-day strategy generated +5.5% net yield on the BTC position (Sharpe on the overlay: 0.53), offsetting roughly a third of BTC's -19.4% spot decline. 16 trades; 13 expired worthless, 3 overrun. Blended portfolio Sharpe improved from -0.47 to -0.39. Max drawdown reduced from 49.7% to 44.5%.
	- **Full period unfiltered (Oct 2021 - Apr 2026):** Same strategy produced -0.5% net yield (-0.1% annualized). Profit factor of 1.00. Win/loss ratio of 4.38:1 -- four winning trades for every loser, yet money lost overall. This is the "pennies in front of a steamroller" result: small consistent wins, large clustered losses in the 2023-2024 recovery rally and 2025 bull market.
	- **Full period with regime filter:** Net yield turned to +23.7% (+5.2% annualized). Blended portfolio Sharpe improved from 0.20 to 0.30. Sortino from 0.27 to 0.39. Strategy was active only 44% of the time. Win/loss ratio declined from 4.38:1 to 2.47:1 (more stop-outs, but far fewer catastrophic losses).
- ## Three Institutional Profiles
	- **Consistency-oriented mandate:** 10-15 delta, 30-60 day expiry. Every tested configuration produced a positive worst-decile 3-year outcome; 93%+ of all 3-year windows positive. Lowest median yields in the productive corridor but highest consistency. Appropriate when capital preservation and predictability matter more than maximizing income.
	- **Balanced yield mandate:** 15-20 delta, 30-day expiry. Near-universal positive 3-year outcomes combined with median yields meaningfully above the conservative corner. Aligns with the most liquid point on the Deribit volatility surface, minimizing execution slippage. The institutional sweet spot for most mandates.
	- **Yield-maximization mandate:** 20-25 delta, 60-90 day expiry. Highest median 3-year yields in the entire tested grid (into double digits in the best decile). Wider single-window dispersion: acceptable for long-horizon allocators who can tolerate variance in annual outcomes but unacceptable for those with shorter reporting cycles or tighter drawdown limits.
	- Two conditions hold across all three profiles without exception: (1) a regime filter must be active; (2) the evaluation horizon must be measured in years, not months.
- ## Caveats & Edge Cases
	- **Short-dated options are structurally broken on BTC:** 7-day and 14-day tenors consistently showed the widest downside tails and lowest medians across all delta levels in the study. BTC's intraday volatility triggers stop-loss exits before theta decay can accumulate. Do not apply conventional equity-options wisdom about short-dated theta harvesting to BTC.
	- **Above 25-delta, the regime filter cannot save you:** At 30-delta and above, directional exposure during bull runs overwhelms the filter. No configuration at this level was a consistent top performer by blended Sharpe.
	- **The strategy is not a hedge:** Covered call writing reduces volatility and provides modest income cushioning, but does not significantly protect against drawdowns in the underlying. The 4.4-5.1 percentage point drawdown improvement in the simulations is the mechanism in action -- income cushioning, not tail protection.
	- **Single-period analysis limitation:** The full-period grid tests one specific and unrepeatable sequence of regimes. Rolling window analysis (37,000+ backtests) addresses this directly and confirms the productive corridor's robustness, but no backtest eliminates regime-sequence risk entirely.
	- **The framework is a floor, not a ceiling:** The simulations hold position size constant, treat the volatility surface as a single number, and ignore term structure dynamics, skew signals, and flow data. Professional managers with access to those inputs can improve on every metric reported.
	- **Market institutionalization risk:** Whether BTC's fat volatility risk premium is a structural feature or a transitional artifact is an open question. The premium could compress as the sell-side of BTC optionality matures.