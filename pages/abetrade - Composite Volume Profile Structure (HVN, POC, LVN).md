author:: [[abetrade]]
summary:: A framework for reading composite volume profiles by identifying three structural zones -- High Volume Nodes (HVN), Points of Control (POC), and Low Volume Nodes (LVN). HVNs and POCs represent areas of fair value and heavy participation where price tends to chop; LVNs are volume voids where price moves quickly. Entries are taken at edges of HVNs or at fast-moving POC tests; targets are set at the next HVN or POC.
category:: [[framework]]
sub-cat:: [[price-action]]
timeframe:: [[intraday]], [[swing]], [[position]]
market:: [[all]], [[crypto]]
instrument:: 
tools:: [[volume profile]], [[composite volume profile]], [[HVN]], [[LVN]], [[POC]]
difficulty:: [[intermediate]]
source:: [https://education.tradingriot.com/volume-trading-analysis/](https://education.tradingriot.com/volume-trading-analysis/)
association:: 
public:: true
status:: [[draft]]

- # abetrade - Composite Volume Profile Structure (HVN, POC, LVN)
- ## TL;DR
	- A composite volume profile maps all volume traded across all visible bars onto the price axis, revealing where large participation occurred (HVNs and POC) and where it didn't (LVNs). Price moves slowly through HVNs and fast through LVNs. Entries belong at HVN edges or fast-moving POC tests; targets belong at the next HVN or POC across the profile.
- ### Context
	- Standard support and resistance drawn from candle highs and lows misses the underlying reason those levels hold: they are often where the most volume was traded. A composite volume profile exposes the full participation structure of the market, letting traders distinguish between levels that are likely to cause chop and levels that will allow fast, clean moves.
- ## Core Concept
	- Markets are auction processes where buyers and sellers negotiate fair value. Most volume concentrates at fair value (HVNs/POC), and price moves rapidly through areas where no agreement was reached (LVNs).
	- The composite profile aggregates all volume across all visible chart bars onto the y-axis (price). The author prefers using all visible bars rather than splitting by fixed periods (weekly/monthly), though fixed-period profiles are also valid.
	- Three structural elements define how price behaves:
		- HVN (High Volume Node): large executed volume. Choppy, range-bound behavior. Good targets; poor entries.
		- POC (Point of Control): the single price level with the highest executed volume inside an HVN. Most "fair" price. Also good targets. Exception: fast rallies directly into an aged POC can provide fade/reversion trades.
		- LVN (Low Volume Node): volume void. Price moves quickly through these levels. Good entry zones; good targets from opposite HVN edges.
- ## Mechanics
	- Plot a composite volume profile covering all relevant visible bars (adjust as price moves and new volume builds).
	- Identify HVN clusters and LVN gaps across the profile.
	- Mark the POC within each HVN.
	- For entries: look for price approaching the edge of an HVN or a fast, impulsive move into an aged POC.
	- For targets: use the next HVN or POC in the direction of the trade.
	- Combine with standard support and resistance, moving averages, or other tools for additional confluence.
	- Update profile regularly -- as markets move, volume builds at new levels and old levels lose relevance.
- ## Entry / Trigger
	- Enter at the edge of an HVN (where price transitions from an LVN into an HVN) -- these areas offer defined risk with a clear level to trade against.
	- Enter on fast, impulsive moves directly into an aged POC (fading trade) when supported by other confluence.
- ## Risk Management
	- Avoid initiating trades inside HVNs or at POCs -- prone to being chopped out before the move resolves.
	- Invalidation: price accepting through the HVN edge and holding inside the HVN suggests the level is being absorbed rather than rejected.
- ## Examples
	- ETH daily chart from the article (early 2023): composite profile built from visible daily bars identified HVN and LVN zones. When revisited weeks later, price respected these levels as dynamic support and resistance without any adjustments -- demonstrating the predictive value of the initial structure.
- ## Caveats & Edge Cases
	- Profiles must be updated as markets move -- a composite built on old data loses accuracy as new volume accumulates at different levels.
	- LVN-based fast moves only hold when there is genuine absence of historical volume. Thin areas on newer assets or low-liquidity markets may not behave the same way.
	- Trading inside HVNs is possible with additional confluence (order flow, pattern recognition) but requires much higher precision and is not the core use case for this framework.
	- The author notes the exact process of using composite profiles is covered in depth in the Tradingriot Bootcamp -- the article covers structural fundamentals only.