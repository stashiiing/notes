author:: [[52kSkew]]
summary:: Funding rate is a delayed lagging indicator — by the time it prints, the positioning has already happened. The edge is reading the underlying delta directly via footprint, where you can see large participants scaling in (consistent same-size passive delta prints) before that activity ever shows up in funding. This gives a minutes-to-hours window to front-run their move.
category:: [[concept]]
sub-cat:: [[orderflow]], [[quantitative]]
timeframe:: [[scalp]], [[intraday]], [[swing]]
market:: [[crypto]]
instrument:: [[perps]]
tools:: [[footprint]], [[delta]], [[CVD]], [[funding-rate]], [[open-interest]]
difficulty:: [[advanced]]
source:: https://youtu.be/9RfaYtbhxfE?t=1750 29:10
association:: 
public:: true
status:: [[draft]]

- {{video https://youtu.be/9RfaYtbhxfE?t=1750}}
- # OI & Funding Rate Pre-Positioning via Delta
- ## TL;DR
	- Funding rate is the lagged average of the past 8 hours — useful, but always behind the actual positioning that's driving the move. Open interest tells you net flow but on a delay too. The real signal is in footprint: large participants scaling positions show up as either heavy negative/positive delta (aggressive market activity) or as consistent same-size delta prints (passive limit scaling). Reading these gives a minutes-to-hours window before funding catches up.
- ### Context
	- Most traders watch funding and OI as primary indicators. By the time funding flips heavily negative or OI spikes, the move is well underway and the large participant is often already done. The point of monitoring delta directly is to see the *cause* of the funding move before the funding move prints.
- ## Core Concept
	- Funding rate ≠ instantaneous true value. It resets to the average of the past 8 hours. So any "current" funding reading reflects an average of stale positioning. Footprint delta is the live data. If you see a participant scaling shorts via market orders, that's negative delta clustering before funding turns negative. If they're scaling via limits, that's consistent same-size passive prints — which funding won't reflect for hours.
- ## Mechanics
	- **Aggressive scaling read.** Heavy negative delta over multiple bars = market-order shorting in size. This will eventually drag funding negative.
	- **Passive scaling read.** Consistent same-size positive (or negative) delta — e.g. +2M, +2M, +2M — indicates a single participant scaling on limits at a target average price. They are not trying to move price; they are accumulating or distributing.
	- **Cross-reference OI.** Heavy shorting in the prior period drags OI in that direction. When the position exits or covers, OI swings the other way.
	- **Window of advantage.** Once you see the scaling, you have minutes-to-hours before the move plays out and funding catches up. Position before the rest of the market reads the lagged signal.
	- **Filter by venue.** Binance is the cleanest data for this — least noisy. Coinbase uses a separate institutional book. Hyperliquid is noisier (degens "yellowing in the price all the time") and needs heavy size-filtered CVD (filter at 100k / 1M / 5M) to be useful.
- ## Entry / Trigger
	- Trigger when footprint shows clear scaling — either aggressive delta clustering or consistent same-size passive prints — at a higher-timeframe level. Enter in the direction of the scaling participant, before funding reflects the activity.
- ## Risk Management
	- Stops outside the participant's scaling zone — if they're scaling shorts at an average price and price extends meaningfully past it, they're either being overrun or the scaling has paused. Either way the thesis is on hold.
- ## Examples
	- Altcoins make the signal especially obvious — Zcash is mentioned as an example where one whale or coordinated group can move price 10–20–50% with footprint clearly visible.
- ## Caveats & Edge Cases
	- DEX hourly funding (vs CEX 8-hour) feels faster but is noisier — don't read DEX funding as cleaner just because it updates more often.
	- Footprint reading is a high-skill activity. Misreading passive absorption as aggressive scaling (or vice versa) flips the direction of the trade.