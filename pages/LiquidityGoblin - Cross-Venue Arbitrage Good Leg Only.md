- author:: [[LiquidityGoblin]]
  summary:: Rather than executing both legs of an arbitrage atomically (buy cheap, sell expensive in the same transaction), this approach takes only the mispriced leg and exits on a more liquid, lower-cost venue. Retaining the good leg dramatically increases net edge by avoiding the transaction costs and gas fees of the exit leg.
  category:: [[strategy]]
  sub-cat:: [[arbitrage]], [[algorithmic]]
  timeframe:: [[scalp]]
  market:: [[crypto]]
  instrument:: [[spot]], [[perps]]
  tools:: [[flash loans]], [[DEX]], [[CEX]]
  difficulty:: [[intermediate]]
  source:: https://www.youtube.com/watch?v=wm1P8im1fuE&t=2014s [33:34]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=wm1P8im1fuE&t=2014s}}
- # Cross-Venue Arbitrage: Good Leg Only
- ## TL;DR
	- Classic atomic arbitrage captures a spread by buying on a cheap venue and instantly selling on an expensive one within a single transaction, sharing most of the profit as gas. Taking only the underpriced leg and exiting on a liquid, low-fee venue (e.g. Binance) keeps two to four times more of the edge per trade.
- ### Context
	- Atomic MEV arbitrage on Ethereum and other chains requires flash loans and smart contracts to execute both legs in the same block. Competing bots bid away nearly all profit in gas. Recognising that one leg is always fairly priced relative to centralised venues, a trader can simply take the mispriced side and exit wherever fees are lowest, at the cost of holding the position briefly.
- ## Core Concept
	- In any cross-venue arb, one venue is mispriced relative to a reference (e.g. Binance spot). The "good leg" is the trade on the mispriced venue. The "bad leg" is closing on a venue with high fees (e.g. a DEX with a 20 basis point fee) or paying gas for an atomic exit. By holding the good leg and selling on a liquid centralised venue, the trader captures the full spread minus only the low taker fee on exit.
- ## Mechanics
	- Monitor DEX prices against a centralised reference venue in real time.
	- When a DEX quotes a token below the reference price by more than the combined round-trip fee (entry DEX fee + CEX taker fee), a valid opportunity exists.
	- Buy on the DEX (the cheap, mispriced side).
	- Hold the position.
	- Sell on the centralised reference venue, where the taker fee is typically 3 to 5 basis points rather than 15 to 20 basis points on a DEX.
	- Do not use a flash loan or atomic exit; the brief holding period is acceptable given the much larger share of edge retained.
- ## Entry / Trigger
	- DEX mid-price deviates from the centralised reference by more than the total round-trip cost (DEX fee + CEX taker fee + slippage estimate). Magnitude of the deviation relative to available liquidity determines position size.
- ## Risk Management
	- The holding period between DEX entry and CEX exit introduces directional risk. Size positions so that a moderate adverse move during the exit window does not eliminate the edge.
	- On large trades (e.g. $200,000 notional), a 40 basis point edge retaining 20 basis points after the cheap exit leg still outperforms an atomic trade that pays 20 basis points to exit atomically and then pays a further portion as gas.
	- Monitor for situations where the DEX price gap is not a genuine mispricing but a sign of low liquidity or stale oracle data, which can produce adverse selection on entry.
- ## Examples
	- A DEX quotes Token A at 40 basis points below Binance spot. Atomic arbitrage would buy on the DEX and sell on another DEX with a 20 basis point fee, keeping 20 basis points before gas. Instead, buying on the DEX and selling on Binance at a 4 basis point taker fee retains 36 basis points, nearly doubling the net edge on the same trade.
	- During early Uniswap and SushiSwap days, flash loan arbitrage was viable. As gas costs rose and competitors multiplied, bidding 95 to 96% of profit in gas made atomic arb uneconomic at most trade sizes. Switching to the good-leg-only approach restored profitability.
- ## Caveats & Edge Cases
	- The brief holding period means the strategy carries delta risk. In fast-moving markets, the reference price can move against the position before the exit is executed.
	- Wash-traded or low-liquidity DEXes may show apparent mispricings that are not real; verify that the DEX has genuine order flow before entering.
	- As more participants adopt this approach on a given venue, the mispricing window narrows and may not persist long enough to exit cleanly on the CEX.
