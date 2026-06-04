- author:: [[abetrade]]
  summary:: The spot order book provides the full depth of resting limit orders and is a more reliable signal than the perpetual book because real capital must back each spot order. The most useful read is the bid-ask skew: the imbalance between total bids and total asks within a band around the current price. Heavy bid skew marks a market that is hard to push down; heavy ask skew marks one that is hard to push up. It is most useful in ranges and as confluence with the derivatives data, not as a standalone entry signal.
  category:: [[concept]], [[framework]]
  sub-cat:: [[orderflow]]
  timeframe:: [[swing]]
  market:: [[crypto]]
  instrument:: [[spot]]
  tools:: [[order book]], [[market depth]]
  difficulty:: [[intermediate]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Spot Order Book and Market Depth Analysis
- ## TL;DR
	- The full depth of the spot order book is public and standard on every major crypto venue, unlike traditional futures or forex where full depth is costly or nonexistent. Spot orders are more informative than perp orders because they require actual capital rather than just margin. The key metric is bid-ask skew: a book with far more bids below than asks above is hard to push down. Spoofing is rampant so individual price levels are unreliable; the shape of the book is what matters. Most effective in ranging conditions and as confluence, not as a standalone entry trigger.
- ### Context
	- Spot is where participants with real capital operate. While perps drive most volume, large spot participants are the ones who can actually push price sustainably. Reading where they are positioned adds a layer of confirmation that is not available in traditional markets with opaque or costly order book data.
- ## Core Concept
	- The order book is the stack of resting limit orders: bids to buy below the current price and asks to sell above it. Plotting size by price level produces a market depth chart; adding colour for size over time produces a heatmap.

	  The number that matters is the skew: the imbalance between total bids and total asks within a defined band around price. A heavy bid skew means more capital is queued to buy below than to sell above, making it harder for sellers to push price down. The reverse is true for heavy ask skew.

	  Spot books carry more information than perp books because to place a large resting bid in spot you need the actual cash or coins behind it, not just margin. Perp books are dominated by market makers quoting both sides to earn the spread with no directional view, and cheap leverage makes spoofing straightforward.
- ## Mechanics
	- Do not read individual price levels. Read the shape: the aggregate imbalance across a band of levels.
	- Skew = total bid depth within the band minus total ask depth, expressed as a ratio or directional indicator.
	- Heavy bid skew: hard to push down; tends to mark range support or the early stage of a new uptrend where spot is absorbing selling.
	- Heavy ask skew: hard to push up; tends to mark range resistance or distribution.
	- Most useful when combined with derivatives data (open interest, funding) pointing in the same direction.
- ## Caveats & Edge Cases
	- Spoofing is rampant in crypto. Large orders that disappear before they are hit are common. Reading single levels is a reliable way to be misled.
	- In a strong trend, price chews through bids and asks regardless of skew. Order book skew works best in ranging conditions; it loses predictive value once a trend is clearly underway.
	- Spot players are patient. A heavily skewed book can stay that way for far longer than a leveraged trader can remain solvent waiting for the mean-reverting move.
	- Treat as confluence. It keeps the trader on the same side as large spot capital and raises conviction, but it does not provide a precise entry on its own.
