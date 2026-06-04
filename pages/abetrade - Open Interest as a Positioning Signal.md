- author:: [[abetrade]]
  summary:: Open interest is the total number of contracts currently open and represents committed capital in the market. It distinguishes whether price moves are driven by new money entering or old positions rotating, making it a real-time conviction gauge. In crypto, open interest updates live and aggregated across exchanges on a single continuous contract, giving a structural edge over traditional markets where equivalent data arrives with a day's delay and is fragmented across expirations.
  category:: [[concept]], [[framework]]
  sub-cat:: [[orderflow]], [[quantitative]]
  timeframe:: [[swing]], [[position]]
  market:: [[crypto]]
  instrument:: [[perps]], [[futures]]
  tools:: [[open interest]]
  difficulty:: [[intermediate]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Open Interest as a Positioning Signal
- ## TL;DR
	- Open interest counts the contracts that are open and not yet closed. It tells you how much capital is committed, not just how much changed hands. Rising open interest alongside a price move means new money is entering the market; falling open interest means positions are closing. A violent drop in open interest is almost always a liquidation wave. Standardised as a z-score, open interest extremes become measurable across all coins on a single scale and are one of the primary inputs for identifying high-conviction trade setups.
- ### Context
	- In derivatives markets, every trade requires a buyer and a seller, so "more buyers than sellers" is meaningless. What changes is whether participants are opening or closing positions. Open interest captures this and is the primary way to distinguish genuine conviction from rotation of existing positions.
- ## Core Concept
	- For every long there is always a short. The balance between the two sides is always equal by definition. What changes is who holds those positions and whether they are opening or closing.

	  Three situations exist: both sides open new positions and open interest rises; both sides close and it falls; one side opens while the other closes and it stays flat.

	  Price moves because market makers hedge their book. When a directional trader goes long, the market maker takes the short and immediately hedges by buying spot or the same contract elsewhere. That hedging pushes price. Rising open interest alongside rising price indicates new directional money is committing, not rotation. A sharp violent drop in open interest is nearly always a forced liquidation event.

	  In crypto, open interest is live, aggregated across exchanges, and on a single continuous contract. On CME, equivalent data arrives once a day and is fragmented across multiple expiration dates.
- ## Mechanics
	- Rising price + rising open interest: new money entering; a healthy trend signal.
	- Falling price + falling open interest: positions closing; less conviction in the direction.
	- Sharp violent drop in open interest: liquidation wave; forced exits compressing a cluster of positions.
	- Price grinding lower + open interest rising + negative premium: a short base building, which can set up a short squeeze.
	- Rotate open interest into a z-score over a rolling 30-day window. Readings above +2 or below -2 standard deviations mark statistically unusual positioning extremes.
	- At market highs, open interest tends to be elevated (participants are structurally long). At lows, it tends to be depressed.
	- Open interest rotates toward altcoins during euphoric markets and concentrates back into Bitcoin during fearful ones.
- ## Examples
	- HYPE: Price ground lower while open interest kept climbing and the premium stayed negative. An aggressive short base built up, which then unwound in a textbook short squeeze.
	- PENGU: Open interest sat flat around 40 to 50 million for months, then exploded to 290 million as the coin rallied. Muted and negative funding throughout confirmed the rally was led by spot demand rather than crowded leveraged longs.
- ## Caveats & Edge Cases
	- Open interest alone does not tell you which direction the new positions are biased. It must be combined with funding and price direction to distinguish a long base from a short base.
	- Large clusters of open interest act as gravity and can become self-fulfilling levels that the market defends or, when it cannot, that trigger cascading forced exits.
