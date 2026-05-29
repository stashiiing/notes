author:: [[abetrade]]
summary:: Relative volume (rVOL) identifies candles with statistically anomalous volume by measuring bars against a rolling fair value baseline. Bars beyond two standard deviations above fair value signal either genuine breakouts initiated by large players or exhaustion/FOMO at the end of moves. Low relative volume areas mark thin participation zones that can serve as trade targets.
category:: [[concept]]
sub-cat:: [[price-action]]
timeframe:: 
market:: [[all]], [[crypto]]
instrument:: 
tools:: [[relative volume]], [[standard deviation]], [[support and resistance]]
difficulty:: [[beginner]]
source:: [https://education.tradingriot.com/volume-trading-analysis/](https://education.tradingriot.com/volume-trading-analysis/)
association:: 
public:: true
status:: [[draft]]

- # abetrade - Relative Volume (rVOL) Confluence
- ## TL;DR
	- Instead of reading every volume bar in isolation, rVOL highlights only the bars that are statistically significant -- those more than two standard deviations above or below the rolling volume fair value. High rVOL marks genuine participation events. Low rVOL marks voids that price tends to revisit quickly.
- ### Context
	- Reading absolute volume bar by bar is noisy and uninformative. The key signal is when volume is abnormally high or low relative to recent history. By applying a standard deviation envelope to the running volume of any asset, traders can isolate only the candles that carry real information about large-player activity or market exhaustion.
- ## Core Concept
	- Volume fair value is calculated using the same bell curve logic as auction market theory -- most volume should sit within a normal distribution. Bars beyond 2 standard deviations above this fair value are "high rVOL" and bars below 2 SD are "low rVOL."
	- High rVOL candles (shown as blue in the author's setup): signal either the start of a new move where large participants initiate breakouts, or the end of a move where retail FOMO drives the final push.
	- Low rVOL candles (shown as yellow): signal low participation, often during overnight sessions or weekends. These areas have little interest from large players and can serve as trade targets since price moves quickly through them on revisits.
- ## Mechanics
	- Apply a rVOL indicator to any chart (the author uses the free Koalafied Volume Extension on TradingView).
	- Flag high rVOL candles (2+ SD above fair value) at support and resistance levels -- these are the confirmation events worth acting on.
	- Note low rVOL zones on the chart. When price pulls back toward these areas, expect fast movement through them. Use them as targets rather than entry zones.
	- Combine with basic support and resistance (or moving averages) for trade setups.
- ## Entry / Trigger
	- High rVOL bar breaking out of a support or resistance level confirms large-player participation and can be used as a breakout entry trigger or confirmation.
	- Low rVOL zones can be used as price targets when initiating trades from nearby high-volume areas.
- ## Risk Management
	- Not specifically addressed in the source.
- ## Examples
	- OP perps chart from the article: blue high-rVOL candles mark the starts of new legs and the exhaustion points of existing ones, clustered near support and resistance levels.
	- GMT perps chart: a straightforward setup combining support and resistance, moving averages, and rVOL confirmation to define entries and targets.
- ## Caveats & Edge Cases
	- High rVOL at the end of a move (FOMO candles) looks identical to high rVOL at the start of a move. Context -- whether price is breaking out from a range versus climaxing after a long trend -- is needed to distinguish them.
	- Low rVOL candles are less actionable as standalone signals; their main value is as context for target placement.
	- The standard deviation lookback period of the indicator affects what counts as "high" or "low" -- different settings will produce different signals on the same chart.