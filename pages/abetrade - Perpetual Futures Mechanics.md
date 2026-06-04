- author:: [[abetrade]]
  summary:: Perpetual futures are derivative contracts that track an underlying asset's price, trade with leverage, and never expire. They dominate crypto trading volume and differ from classical futures by replacing expiry-driven convergence with a funding rate mechanism. Understanding their structure is foundational to reading crypto market behaviour.
  category:: [[concept]]
  sub-cat:: [[orderflow]]
  timeframe::
  market:: [[crypto]]
  instrument:: [[perps]], [[futures]]
  tools::
  difficulty:: [[beginner]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Perpetual Futures Mechanics
- ## TL;DR
	- A perpetual future is a derivative contract that tracks the price of an underlying asset, trades with leverage, and never expires. It is the dominant instrument in crypto, accounting for the large majority of all trading volume. Unlike classical futures, there is no expiry to force price convergence with spot, so a funding rate mechanism takes its place as the gravity that keeps the contract anchored.
- ### Context
	- Crypto traders overwhelmingly use perpetual futures rather than spot or dated contracts. Understanding what they are, how they differ from classical futures, and what keeps their price tethered to spot is essential before using any derivatives data in analysis.
- ## Core Concept
	- A classical futures contract expires on a set date, and that expiry forces convergence between the futures price and the spot price via arbitrage. The gap between them before expiry is the basis, reflecting cost of carry, financing, and time remaining. Expiry also creates a term structure: multiple contracts across different dates form a curve, and traders must roll positions across expirations.

	  A perpetual future strips out expiry entirely, giving traders one continuous contract with no rolling required. Because nothing forces it back to spot at expiry, it uses a funding rate instead, a recurring payment exchanged between longs and shorts that penalises whichever side is driving the contract away from spot.
- ## Mechanics
	- A perpetual tracks the underlying asset price and trades with leverage, but has no settlement date.
	- Without expiry, the funding rate replaces the convergence gravity that expiry used to provide.
	- The contract is the dominant crypto instrument because it eliminates rolling friction and concentrates liquidity in a single contract rather than fragmenting it across expiration dates.
	- When the perpetual trades above spot, longs pay shorts via the funding rate, pushing it back down. When it trades below spot, shorts pay longs.
	- The futures term structure (contango and backwardation) in dated markets has an analogue in perps: the funding rate carries the same information about positioning and sentiment that the shape of a futures curve does.
- ## Caveats & Edge Cases
	- Crypto exchanges list dated quarterly contracts alongside perpetuals, and the classical cash-and-carry arbitrage applies to those. Perpetuals are the dominant trading instrument but not the only one.
	- The perpetual is a derivative, so its price can temporarily dislocate from spot during high stress or low liquidity. The funding rate corrects this over time but not instantaneously.
