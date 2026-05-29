author:: [[dlawant]]
summary:: A covered call overlay on BTC shows dramatically different probability of success depending on the evaluation horizon: 55-85% of 1-year windows produce positive yield, but 91-100% of 3-year windows do across the productive parameter corridor. This gap -- the patience premium -- is quantifiable and is the primary argument for measuring the strategy in years rather than months.
category:: [[concept]], [[analysis]]
sub-cat:: [[systematic]], [[quantitative]]
timeframe:: [[position]], [[investing]]
market:: [[crypto]]
instrument:: [[options]], [[spot]]
tools:: [[covered call]], [[rolling window]], [[Sharpe ratio]], [[regime filter]], [[Deribit]]
difficulty:: [[advanced]]
source:: [https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing](https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing)
status:: [[draft]]

- # Patience Premium in BTC Covered Call Writing
- ## TL;DR
	- Rolling window analysis across more than 37,000 individual backtests shows that BTC covered call overlays produce positive yield in only 55-85% of 1-year windows, but in 91-100% of 3-year windows across the productive parameter corridor (10-25 delta, 30-90 day expiry, regime filter active). The gap between those two numbers is what the paper calls the patience premium: the excess return available to investors who can commit to a multi-year horizon rather than evaluating the strategy on an annual basis.
- ### Context
	- BTC's episodic bull and bear cycles mean that any single year of covered call selling is partly a regime bet and only partly a yield strategy. A fund manager evaluated on 12-month performance is running a fundamentally different risk profile than a long-horizon allocator who can average across multiple regimes. This concept quantifies exactly how large that difference is and provides the empirical basis for setting appropriate evaluation horizons in institutional mandates.
- ## Core Concept
	- The patience premium reflects the diversification benefit that comes from allowing the premium collection process to average across multiple BTC market regimes. A single BTC year can be dominated by a violent bull run that overruns short call positions, producing a large negative outcome regardless of how well the strategy is designed. Over three years, the probability that all three calendar years contain a regime hostile to call selling is historically very low, and the accumulated premiums from favorable regimes overwhelm the losses from unfavorable ones for nearly every tested configuration.
- ## Mechanics
	- 37,000+ individual backtests covering every possible 1-year and 3-year rolling start date in the October 2021 to April 2026 dataset.
	- Parameter space tested: 10-, 15-, 20-, and 25-delta crossed with 30-, 60-, and 90-day expiry (12 configurations), all with regime filter active.
	- **At 1-year horizon:** Mean yields are universally positive across all 12 configurations, ranging from roughly +0.2% to +4.6% annualized. However, % Positive (windows with positive yield) ranges from approximately 55% to 85%. Roughly one in four to one in five annual periods produced a loss for most configurations. Distribution shapes are typically bimodal, straddling the zero line, with spreads of up to 20 percentage points between the two modes.
	- **At 3-year horizon:** 11 of 12 configurations reach 91% or above in % Positive. 5 of 12 reach 100%. Median annualized yields cluster between 4% and 6% across the productive corridor, with the best configurations reaching double digits in the top decile. The P10 (worst-decile) outcome is positive for every configuration except 10-delta/90-day DTE. Distributions shift from bimodal to single-peaked and concentrated in positive territory.
	- **The exception:** 10-delta/90-day DTE is the lone configuration where thin premium collected infrequently fails to overcome regime sensitivity even at a 3-year horizon. The left tail on this configuration remains meaningfully wider than others.
- ## Examples
	- An investor who started the 20-delta/30-day filtered strategy at the peak of the 2021 bull market (one of the worst possible entry points) still produced positive annualized yield over any subsequent 3-year window in the dataset.
	- At the 1-year horizon, the same strategy starting in late 2023 or early 2024 -- during the recovery rally -- would have been deeply negative as the strategy was repeatedly overrun even with the filter active.
	- The ridge chart visualization in the paper shows 1-year windows with bimodal distributions straddling zero (regime-dependent outcomes) collapsing into single right-skewed distributions clearly above zero at the 3-year horizon for 11 of 12 configurations.
- ## Caveats & Edge Cases
	- The patience premium only materializes with the regime filter active. Without the filter, longer horizons do not rescue the strategy: the unfiltered full-period result is slightly negative regardless of horizon.
	- The 3-year finding is based on a 4.5-year dataset containing two full bull/bear cycles. A future dataset containing three consecutive years of parabolic bull market would test the robustness of these findings materially.
	- An investor evaluated on annual performance cannot capture the patience premium even if the underlying allocation is long-horizon. The mismatch between evaluation cadence and strategy horizon is an institutional design problem, not just an analytical one.
	- Median yields at the 3-year horizon (4-6% annualized for most configurations) reflect the productive but not extreme corridor of outcomes. The best-decile configurations reaching double digits are real but should not be used as base-case planning assumptions.