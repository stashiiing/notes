author:: [[52kSkew]]
summary:: A scalping technique for slow markets where skew "pokes" the dominant market-maker algo with size to provoke a reaction — the algo, trying to outbid him, market-buys an equivalent amount and lifts price. He then sells into that algo-driven move. Less viable on BTC since October but still works on low-float alts where one MM dominates volume.
category:: [[strategy]]
sub-cat:: [[orderflow]], [[discretionary]], [[algorithmic]]
timeframe:: [[scalp]]
market:: [[crypto]]
instrument:: [[perps]]
tools:: [[footprint]], [[order-book]]
difficulty:: [[advanced]]
source:: https://youtu.be/9RfaYtbhxfE?t=3260 54:20
association:: 
public:: true
status:: [[draft]]

- {{video https://youtu.be/9RfaYtbhxfE?t=3260}}
- # Baiting Market Maker Algorithms
- ## TL;DR
	- In slow markets, MM algos are predictable — bid against you to avoid letting you fill cheaper. Skew exploits this by poking the algo with size on one side. The algo responds by market-buying (or selling) a comparable size to maintain its inventory profile, lifting price. He then sells into that move. The pattern is the same in both directions, creating a "hot potato" exchange between him and the algo where he's intentionally creating liquidity to dump on.
- ### Context
	- Market-maker algorithms are deterministic. They have to respond to certain inventory and order-flow conditions or their model breaks. Once you've identified the trigger conditions, you can repeatedly bait them — especially on shitcoins where one MM dominates 85–90% of the volume.
- ## Core Concept
	- MMs don't want you to buy cheaper than them. When you show large size, their algorithm responds with market activity to "outbid" you. That response *is* the trade — you let them lift price, then sell to them. The relationship is symmetric on the downside.
- ## Mechanics
	- **Identify the dominant MM.** Look for a token where one participant accounts for 85–90% of volume. On these names, MM behaviour is highly mechanical.
	- **Poke with size.** Place visible size on the bid (or offer). The MM algo treats your size as competition and reacts.
	- **Wait for the response.** The algo market-buys an equivalent amount, lifting price.
	- **Sell into the lift.** Exit your position into the algo-driven move. The algo just provided your exit liquidity.
	- **Repeat.** On certain alts this works perpetually — the MM has no choice but to keep responding.
	- **Inverse setup.** When DWF or a similarly directional MM enters and dominates volume (also 85–90%), wait until their share drops back to ~60–65%. That's the cue they're done — they exit (or accumulate) decisively at that moment. Position before the rest of the market notices.
- ## Entry / Trigger
	- Bait trigger: dominant single MM identified, slow market with low organic flow, and your size is large enough to register as competition. Poke, wait for the reaction, sell/buy into it.
- ## Risk Management
	- Tight stops — this is scalp activity. If the algo doesn't respond as expected, exit immediately rather than holding into a different regime. The trade only works while the MM's behaviour profile is intact.
- ## Examples
	- Skew mentions DWF as a directional MM whose dominance pattern was so obvious every trading shop knew about it. Some shops took the opposite side and profited; others got run over and pursued vendettas across DWF's positioned tokens, creating chaos on the affected alts.
- ## Caveats & Edge Cases
	- "I think they tightened a lot of the profiles after October." MM behaviour on BTC and major alts was deliberately changed after the October 2025 wipeout, making the bait less reliable on majors.
	- Still works on lower-float shitcoins where one MM dominates.
	- Requires real size — small accounts won't register as competition and won't trigger a response.
	- This is intentionally adversarial and only relevant for traders with the size and tooling to play that game.