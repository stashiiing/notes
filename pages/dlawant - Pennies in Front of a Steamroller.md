author:: [[dlawant]]
summary:: Short volatility strategies like covered call writing produce many small wins and infrequent but large, clustered losses. In BTC, this dynamic is intensified by the asset's autocorrelated bull markets, where a high win/loss ratio (4+ to 1) can coexist with negative net yield across a full cycle. Understanding this asymmetry is foundational to any disciplined volatility-selling program.
category:: [[concept]], [[philosophy]]
sub-cat:: [[systematic]], [[quantitative]]
market:: [[crypto]]
instrument:: [[options]]
tools:: [[covered call]], [[short volatility]], [[autocorrelation]], [[regime filter]]
difficulty:: [[intermediate]]
source:: [https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing](https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing)
status:: [[draft]]

- # Pennies in Front of a Steamroller: Short Volatility Risk in Trending Markets
- ## TL;DR
	- Covered call writing on BTC is a textbook short volatility strategy: it collects many small premiums in benign environments and periodically suffers large concentrated losses when BTC runs parabolic. The paradox -- four winning trades for every loser, yet negative net yield over a full cycle -- is not a bug but the defining feature of the strategy. It is caused by the asymmetry between the size of wins and losses combined with BTC's autocorrelated bull markets, where losses cluster across consecutive expiry cycles rather than arriving as isolated single events.
- ### Context
	- The most common mistake in implementing yield overlays on volatile assets is evaluating the strategy only by its win rate. A 4:1 win/loss ratio sounds compelling until you understand that the losing trades are three to five times larger than the winning ones. This concept page captures the mental model and mechanics behind that asymmetry, which is the central intellectual prerequisite for building any disciplined BTC volatility-selling program.
- ## Core Concept
	- A short volatility position -- which a short call is -- resembles insurance writing. The seller collects many small premiums and periodically pays out a large claim. The strategy's expected value is positive when implied volatility is consistently richer than realized volatility, which is often true in BTC. But the IV/RV spread is only half the story.
	- The second and more dangerous factor is autocorrelation. When BTC's price moves are serially correlated rather than independent -- as they are during its episodic parabolic bull runs -- large moves cluster in time. A short call seller faces the same trending market across multiple consecutive expiry cycles, not a single shock that mean-reverts. Each new position is opened into a market that has already moved against the previous one. In those moments, short volatility exposure becomes a source of large, concentrated, and repeated losses rather than steady income.
	- The unfiltered 20-delta, 30-day strategy over the full October 2021 to April 2026 period had a win/loss ratio of 4.38:1 and still produced net negative yield. This is the empirical demonstration of the concept.
- ## Mechanics
	- Short call positions have a capped gain (the premium collected) and an uncapped loss (the option can go deeply in the money as BTC rallies).
	- The dollar value of a single losing trade in a strong BTC bull run typically exceeds the aggregate premium collected across multiple prior winning trades.
	- Autocorrelation amplifies this: BTC's bull markets persist for months, meaning not one but three to five consecutive short call positions may all be overrun before the trend reverses.
	- The strategy also embeds negative skewness: it caps the right tail of the blended portfolio's return distribution while leaving the left tail essentially intact. This is the asymmetry that Israelov and Nze Ndong (2023) identified as the core failure mode of high-yield covered call implementations -- the higher the yield target (higher delta), the worse the skewness problem.
	- The only structural defense against this dynamic is a regime filter that prevents new position entry during trending bull markets entirely.
- ## Examples
	- Over the full October 2021 to April 2026 period, the unfiltered 20-delta strategy had 57 winning trades and 13 losing trades (4.38:1 win/loss ratio). Net yield: -0.5% (-0.1% annualized). Profit factor: 1.00. The 13 losing trades roughly equaled in dollar value the aggregate of all 57 winners.
	- The 2023-2024 recovery rally (BTC from roughly $16,000 to over $70,000) and the 2025 bull market (BTC briefly above $100,000) were the two "steamrollers" in this dataset. Multiple consecutive short call positions were overrun in each episode.
	- With the regime filter applied, the same strategy moved to +23.7% net yield over the same period. The filter prevented entry during the most violent bull markets, reducing the win/loss ratio to 2.47:1 but eliminating most of the catastrophic losses.
- ## Caveats & Edge Cases
	- The "pennies in front of a steamroller" dynamic is not unique to BTC -- it is the defining feature of all short volatility strategies in trending markets. What is unique to BTC is the intensity and frequency of the steamrollers.
	- The concept does not imply the strategy is fundamentally broken. The volatility risk premium is real. The problem is exclusively with undisciplined, always-on implementation.
	- The regime filter dramatically improves outcomes but does not eliminate the risk entirely. The filtered strategy still recorded 19 stop-loss exits versus 13 for the unfiltered version; it simply avoided the most devastating clustered losses.
	- Negative skewness is an inherent feature of all short call strategies, not an artifact of BTC specifically. Investors with formal drawdown constraints or risk-budget frameworks should price this skewness explicitly when sizing the overlay.