- author:: [[abetrade]]
  summary:: A framework for using VWAP standard deviation bands (1 SD and 2 SD) both as trend-following zones on strong moves and as mean-reversion triggers when price re-accepts inside the bands. The approach requires strong confluence for mean-reversion trades and is more forgiving when used for trend continuation.
  category:: [[strategy]]
  sub-cat:: [[price-action]], [[orderflow]]
  timeframe:: [[intraday]]
  market:: [[all]]
  instrument:: 
  tools:: [[VWAP]], [[VWAP bands]], [[CVD]], [[footprint chart]]
  difficulty:: [[intermediate]]
  source:: [https://education.tradingriot.com/vwap-trading-strategy/](https://education.tradingriot.com/vwap-trading-strategy/)
  association:: 
  public:: true
  status:: [[draft]]
- # abetrade - VWAP Standard Deviation Bands
- ## TL;DR
	- On strong trending days, price often pulls back only to the 1 SD band rather than all the way to VWAP. Entries can be taken at that band for trend continuation. When price re-accepts inside the 1 SD band, a mean-reversion trade targeting VWAP or the opposite band is possible -- but only with significant order flow confluence.
- ### Context
	- Pure mean-reversion strategies (Bollinger Bands, Keltner Channels, VWAP mean reversion) fail badly on trend days. VWAP SD bands offer a way to participate in both trending and mean-reverting conditions, but the two modes require different approaches to risk and confluence.
- ## Core Concept
	- VWAP standard deviation bands (1 SD and 2 SD above and below VWAP) define zones of statistical significance around the session's volume-weighted average. On strong trend moves, these bands act as dynamic support/resistance that price respects without pulling all the way back to VWAP. When price does re-enter the band after an extended move, a mean-reversion trade toward VWAP becomes available.
- ## Mechanics
	- 1 SD band acts as a support zone on strong bullish trend days; 1 SD band below acts as resistance on bearish trend days.
	- Trend continuation entry: wait for price to pull back to the 1 SD band and show signs of acceptance (order flow confirmation), then enter in the direction of the trend targeting a new high/low or the 2 SD band.
	- Mean reversion entry: when price accepts back inside the 1 SD band (closes back inside it after being outside), take a trade targeting VWAP or the opposite 1 SD band.
	- The author applies much higher confluence requirements for mean reversion versus trend-following entries.
- ## Entry / Trigger
	- Trend continuation: pullback to 1 SD VWAP band with order flow confirmation (CVD, footprint absorption).
	- Mean reversion: price accepts back inside 1 SD band after an extension, targeting VWAP.
- ## Risk Management
	- Mean-reversion trades require much higher confluence -- look for many more confirming factors before entry.
	- One trend day taking the opposite side of an extended move can cause major damage if conviction is low.
	- Not specified further in source.
- ## Examples
	- The article includes a chart showing a long entry at the 1 SD VWAP band supported by bullish Cumulative Volume Delta divergence and footprint chart absorption, which led to a successful mean-reversion back to VWAP.
- ## Caveats & Edge Cases
	- Mean reversion with VWAP bands can work but is not suitable as a standalone or systematic strategy.
	- On strong trend days, price can extend well beyond 2 SD bands -- a position fading at 1 SD would be badly offside.
	- Requires order flow tools to differentiate between genuine exhaustion and a brief pause before continuation.
