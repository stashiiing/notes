author:: [[dlawant]]
summary:: Bitcoin's upside implied volatility has historically and persistently exceeded subsequent realized upside volatility by two to three times the margin seen in SPY or QQQ, creating a structural premium that makes systematic call selling on BTC a fundamentally different proposition than in traditional equity markets.
category:: [[concept]], [[analysis]]
sub-cat:: [[quantitative]], [[systematic]]
market:: [[crypto]]
instrument:: [[options]]
tools:: [[implied volatility]], [[realized volatility]], [[volatility risk premium]], [[25-delta call]], [[Deribit]]
difficulty:: [[intermediate]]
source:: [https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing](https://www.anchorage.com/research/synthetic-yield-on-bitcoin-implementation-discipline-and-performance-boundaries-of-systematic-covered-call-writing)
status:: [[draft]]

- # BTC Upside Volatility Risk Premium
- ## TL;DR
	- Bitcoin's options market consistently prices in more upside volatility than subsequently materializes, and does so by a margin of two to three times what SPY and QQQ deliver. This structural excess -- the volatility risk premium (VRP) -- is the empirical anchor underpinning the institutional case for systematic covered call writing on BTC. The premium is real, persistent, and structurally larger than in traditional asset classes.
- ### Context
	- Institutional allocators evaluating yield-generating overlays on BTC holdings need to understand why the option market chronically overprices upside risk before building any systematic selling program around it. Without confirming the VRP is genuine and persistent, selling calls is speculation on direction rather than a premium-harvesting strategy. The BTC options market has also transformed dramatically: notional open interest has grown roughly ten-fold over five years, briefly broke $100 billion in late 2025, and now exceeds the entire BTC futures market. IBIT options, launched in late 2024, have grown explosively and now rival Deribit as the leading venue. The market institutional allocators face today is broader, deeper, and far more accessible to traditional capital pools than it was even eighteen months ago.
- ## Core Concept
	- The 30-day, 25-delta call implied volatility on BTC has averaged roughly two to three times the subsequent 21-trading-day realized upside volatility, a gap that has been persistent for most of the post-2024 period. SPY and QQQ hover in a narrow band of low single-digit positive premiums. BTC's premium sits structurally above them, occasionally reaching 20 to 30 implied volatility points of forward-looking excess.
	- This pattern aligns with academic predictions on the VRP: option buyers pay a premium for tail protection and convexity, and BTC's structurally higher demand for upside exposure magnifies that premium above what traditional assets command.
	- BTC's 60% call share of open interest, while down from a peak near 70%, still sits roughly 25 percentage points above mature equity index options markets (SPY and QQQ at approximately 34% and 36% respectively as of April 2026). This persistent call-heaviness means sellers of upside consistently receive elevated compensation relative to what the underlying actually delivers.
- ## Mechanics
	- The premium is measured as 25-delta call implied volatility minus realized upside volatility over the subsequent 21 trading days, computed on a like-for-like basis.
	- BTC's premium has averaged two to three times the SPY/QQQ equivalent over the study period.
	- The premium occasionally goes sharply negative when realized upside surprises, with January 2026 being the most prominent example in the dataset. These tail events are the primary risk for any systematic seller.
	- The premium is structurally related to the skew of BTC's open interest toward calls: more buyers of upside means sellers are chronically compensated above actuarial fair value.
- ## Examples
	- Over most of the post-2024 window, BTC's upside VRP registered 10 to 30 volatility points of positive premium versus the subsequent realized move.
	- Both SPY and QQQ showed one sharp negative excursion from the Liberation Day stock market crash in early 2025; BTC showed its own negative tail in January 2026 when realized upside dramatically exceeded what was implied.
- ## Caveats & Edge Cases
	- The premium is not constant. Episodes of violent upside in BTC (parabolic bull markets) flip it sharply negative, meaning systematic sellers face left-tail losses that are large, clustered, and autocorrelated -- not random.
	- The BTC options market is institutionalizing rapidly. Whether the fat premium is a structural feature or a transitional artifact of a maturing market is an open empirical question the author intends to revisit as the sample grows.
	- Deribit data underpins the analysis. CME and IBIT options are noted as having persistently higher call premiums than Deribit but introduce their own constraints: limited trading hours, overnight gap risk, and more complex risk management requirements.