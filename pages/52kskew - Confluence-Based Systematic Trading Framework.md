author:: [[52kSkew]]
summary:: A layered confluence approach to trading where each trade must pass multiple independent checks — price action at a key level, higher-timeframe trend alignment, systematic momentum confirmation, and order flow validation. The goal is to stack as many "absoluteness" factors as possible so the long/short decision is no longer speculative.
category:: [[framework]]
sub-cat:: [[price-action]], [[systematic]], [[orderflow]], [[discretionary]]
timeframe:: [[intraday]], [[swing]]
market:: [[crypto]]
instrument:: [[perps]], [[spot]]
tools:: [[RSI]], [[moving-averages]], [[VWAP]], [[CVD]], [[footprint]], [[TradingView]]
difficulty:: [[intermediate]]
source:: https://youtu.be/9RfaYtbhxfE?t=720 12:00
association:: 
public:: true
status:: [[draft]]

- {{video https://youtu.be/9RfaYtbhxfE?t=720}}
- # Confluence-Based Systematic Trading Framework
- ## TL;DR
	- 52kskew's core framework stacks four independent confirmations before entering a trade: price action at a higher-timeframe level, trend/structure alignment, systematic indicator confirmation (RSI + moving averages), and order flow validation of organic participation. Each layer answers a different question, and only when they agree does the trade become "absolute" rather than speculative.
- ### Context
	- Most retail traders pile on indicators without a hierarchy and end up speculating with extra steps. Skew built this stack after burning through the typical journey — random indicators, diagonal trendlines, fake-outs — and concluded that absoluteness comes from independent confirmations, not more of the same signal.
- ## Core Concept
	- A trade is only worth taking when multiple unrelated signals agree on direction. Price action tells you *where*. Structure and trend tell you *which way*. Systematic indicators tell you if there's *momentum*. Order flow tells you if the move is *real* or one player painting the tape. Each layer filters out a different failure mode.
- ## Mechanics
	- **Layer 1 — Price action & key levels.** Identify higher-timeframe horizontal levels where price has reacted repeatedly (weeks/months). These feed breakouts and breakdowns. Diagonal trendlines are mostly noise except on the highest timeframes.
	- **Layer 2 — Structure & trend.** Higher highs / higher lows = uptrend, opposite for downtrend. Trade is taken in the direction of the higher-timeframe trend.
	- **Layer 3 — Systematic confirmation.** RSI > 50 for longs (momentum filter). Price trading above/below relevant moving averages (e.g. 4H 50 EMA and 4H 200 EMA on a daily-trend setup). Algorithms widely respect VWAPs and standard MAs, which makes them self-reinforcing.
	- **Layer 4 — Order flow.** Final filter. Is there genuine organic buying/selling via CVD, delta, and footprint? Or is one participant moving price alone? If it's the latter, you ride the move until they stop and then fade them.
- ## Entry / Trigger
	- All four layers aligned in the same direction. Specifically for an alt long: price reclaims a higher-timeframe level (e.g. 1W low or 1D higher high), RSI > 50, price above 4H 50/200 EMAs, and order flow shows organic buying rather than a single participant.
- ## Risk Management
	- Trailing stop based on a moving average (e.g. a higher-timeframe EMA) lets the position capture the trend and exit in profit when the structure breaks. Position is sized 1–5% of portfolio per name on early scaling entries.
- ## Examples
	- The post-November 2024 election move: vertical leg, then grind higher with momentum loss visible on the higher timeframe, then a pullback that didn't break the higher-timeframe trend — a confluence reset rather than a reversal.
- ## Caveats & Edge Cases
	- During ranges, the framework doesn't fire — the trend layer is absent, so confluence collapses. Switch to range trading or scalping in those regimes.
	- Confluence is not a guarantee — it's a probability stack. Single-participant moves can override even good setups; that's what the order-flow layer exists to catch.