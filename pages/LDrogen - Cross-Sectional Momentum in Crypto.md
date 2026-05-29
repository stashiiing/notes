author:: [[ldrogen]]
summary:: Starkiller's trend strategy is built on two layers: time-series momentum (long above the 50-day moving average, flat below) and cross-sectional momentum (long the top 20th percentile of tokens by 30-day performance, short the bottom 20th percentile). A fundamental overlay filters out assets with no intrinsic value on the long side and reduces short-squeeze risk on the short side. The strategy is particularly powerful in crypto because most assets have no intrinsic value, making price momentum the dominant signal.
category:: [[strategy]]
sub-cat:: [[systematic]], [[quantitative]]
timeframe:: [[swing]], [[position]]
market:: [[crypto]]
instrument:: [[spot]], [[perps]]
tools:: [[momentum]], [[moving-average]], [[cross-sectional]], [[position-sizing]], [[fundamental-overlay]]
difficulty:: [[advanced]]
source:: https://youtu.be/eT4iZzJXCyA [00:33:22]
status:: [[draft]]

- {{video https://youtu.be/eT4iZzJXCyA?t=2002}}
- # Cross-Sectional Momentum in Crypto
- ## TL;DR
	- A long/short momentum strategy in digital assets combining time-series trend following with weekly cross-sectional momentum signals. Long the top 20th percentile of tokens by 30-day return, short the bottom 20th percentile. Overlaid with a fundamental filter that avoids pure Ponzi schemes on the long side and reduces exposure to market structure manipulation on the short side. Momentum works especially well in crypto because most assets have zero intrinsic value, leaving price behaviour as the dominant signal.
- ### Context
	- Momentum is the only persistent alpha across all asset classes because it is the only signal rooted in a durable behavioural characteristic of humans. All other alpha eventually gets arbitraged away through better data, compute, or regime changes. Human behaviour does not change. In crypto specifically, the absence of intrinsic value in the vast majority of tokens means there is no fundamental anchor to compete with or dampen the momentum signal.
- ## Core Concept
	- Two momentum layers operating together: (1) time-series trend on the asset class level be long when Bitcoin is above its 50-day MA, flat or short when below; (2) cross-sectional momentum within the asset universe rank all tokens by 30-day return each week, go long the top 20th percentile, short the bottom 20th percentile. Fundamental overlay adds a quality filter: avoid assets with no plausible path to intrinsic value on the long side; avoid highly illiquid or manipulated tokens on the short side.
- ## Mechanics
	- **Time-series momentum layer:**
		- Use a 50-day moving average on Bitcoin (or broader market) as the macro regime filter.
		- Be long (or net long) when price is above the 50-day; reduce or exit when below.
	- **Cross-sectional momentum layer:**
		- Weekly rebalance cadence.
		- Rank all eligible tokens by 30-day return.
		- Long book: top 20th percentile. Concentrated typically no more than 20-25 names.
		- Short book: bottom 20th percentile. More diversified than the long book.
	- **Fundamental overlay:**
		- Long side: favour tokens with some intrinsic value, real revenue, or genuine institutional adoption. Example: Hyperliquid has actual fee revenue and reasonable tokenomics.
		- Long side: de-weight or exclude tokens with large upcoming unlock schedules that are not growing users.
		- Short side: higher liquidity floor use only tokens with sufficient open interest on perp DEXs to get adequate size without excessive funding rate squeeze risk.
		- Short side: assess probability of market structure manipulation ("shit risk") teams or market makers artificially pumping prices; avoid concentrated short positions where this is elevated.
	- **Liquidity rules:**
		- All positions sized so the fund can exit within a defined maximum period (well under one week).
		- Long book: lower market cap / liquidity floor acceptable; longer-tail names allowed.
		- Short book: higher market cap / liquidity floor required; smaller tokens excluded due to perp open interest constraints and squeeze risk.
- ## Entry / Trigger
	- Long entry: token ranks in top 20th percentile of 30-day return in weekly rebalance AND passes fundamental overlay AND market regime filter is positive (above 50-day MA).
	- Short entry: token ranks in bottom 20th percentile of 30-day return in weekly rebalance AND passes liquidity and "shit risk" filters.
- ## Risk Management
	- Long positions: willing to be more concentrated; momentum bend-over triggers exit.
	- Short positions: deliberately diversified to limit exposure to any single manipulation event; no hard percentage cap but position size governed by liquidity floor and FDV parameters.
	- Fundamental overlay prevents holding momentum longs that have deteriorated in user growth and are facing heavy token unlocks.
	- When a token pumps in correlation with Bitcoin off a bottom (L1/L2 beta bounce), recognise that those tokens require additional real capital inflows to sustain momentum absent that, the pump reverts as holders sell into it.
- ## Examples
	- Simple baseline outperformance: a 50-day MA strategy on Bitcoin alone long above, flat below would massively outperform buy-and-hold by avoiding the major drawdowns.
	- Cross-sectional baseline: buying top 20th percentile and shorting bottom 20th percentile with no other filter would generate significant positive returns in backtests; operational constraints prevent running it in pure form.
	- Hyperliquid cited as a prototypical quality long: actual revenue, sensible tokenomics, direct relationship between business performance and token value.
	- Most L1/L2 governance tokens cited as structural shorts: no intrinsic value, persistent unlock pressure, no moat.
- ## Caveats & Edge Cases
	- "Shit risk" on shorts: small/mid-cap tokens are vulnerable to coordinated price manipulation, perpetual futures funding rate squeezes, and team/market maker activity. Diversification mitigates but does not eliminate this.
	- Vampire attack risk on longs: a competing protocol can fork and drain liquidity from a previously strong protocol with no moat, invalidating the momentum thesis quickly.
	- Momentum in crypto is strong partly because of the low intrinsic value of most assets. If tokenomics evolve toward more cash-flow-generative models, cross-sectional momentum may weaken relative to fundamental factors.
	- Strategy is long beta in bull markets: the combination of long top performers and short bottom performers still carries meaningful net long exposure in trending up-markets.