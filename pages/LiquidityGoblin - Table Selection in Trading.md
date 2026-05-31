- author:: [[LiquidityGoblin]]
  summary:: The most reliable way to improve trading profitability is not to become a better trader but to find markets and venues where counterparties are less sophisticated. Like a poker player who avoids the pros and seeks out recreational players, a trader who selects inefficient venues with unsophisticated flow will outperform one with superior skill at a competitive venue.
  category:: [[philosophy]]
  sub-cat:: [[discretionary]], [[philosophy]]
  timeframe:: 
  market:: [[all]]
  instrument:: 
  tools:: 
  difficulty:: [[beginner]]
  source:: https://www.youtube.com/watch?v=wm1P8im1fuE&t=2420s [40:20]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=wm1P8im1fuE&t=2420s}}
- # Table Selection in Trading
- ## TL;DR
	- Choosing where to trade matters more than how well you trade. A trader of average skill at the right venue will consistently outperform a highly skilled trader at the wrong one. Seek out markets with low volume, low sophistication, and a mismatch between liquidity and flow — the equivalent of sitting with recreational poker players rather than professionals.
- ### Context
	- Most retail and semi-professional traders focus on improving their analytical edge while ignoring the competitive environment they trade in. In practice, a trader cannot improve their skill in the five minutes before they start; they can, however, choose a better table. This principle applies across market-making, arbitrage, and discretionary trading.
- ## Core Concept
	- Trading is a zero-sum game at the margin. Profit comes from counterparties making mistakes. The rate and magnitude of those mistakes is higher where participants are less informed, less equipped, or trading for non-economic reasons (e.g. farming points, completing incentive programmes). Selecting those venues is the highest-leverage improvement available to a smaller trader.
- ## Mechanics
	- Evaluate venues and markets on the following dimensions before deploying capital:
	- **Volume relative to liquidity**: A venue where volume is high relative to book depth suggests active but unsophisticated flow. Large market orders sweeping multiple levels of the book ("pay-throughs") are visible in candlestick data and indicate low-quality order flow.
	- **Liquidity relative to volume**: A venue where a market maker is contractually required to provide depth but volume is thin means transaction costs are low and even small edges can be extracted cheaply.
	- **Participant sophistication**: New venues, new chains with poor tooling, and DEXes without Telegram bots or aggregator routing are likely to have less sophisticated participants. If trading there is annoying and technically painful, that friction is the edge.
	- **Non-economic flow**: Participants farming points or airdrop allocations through volume are indifferent to execution quality. They represent predictable, exploitable counterparty behaviour.
	- **Visible order flow**: On transparent chains, large TWAPs and block trades are publicly readable. A participant executing a known TWAP programme is a predictable, front-runnable counterparty.
	- Avoid venues with high HFT and market maker participation relative to volume: Binance BTC/USDT, CME ES futures, and similar deep liquid markets are the "pro tables."
- ## Examples
	- HyperLiquid spot markets at launch showed egregious price discrepancies relative to centralised reference venues, indicating unsophisticated participants and a clear arbitrage opportunity for anyone monitoring the spread.
	- A participant executing a TWAP on HyperLiquid via the standard UI broadcasts the full parameters on-chain (size, duration, direction). Any observer can trade in the same direction and scalp the predictable price impact.
	- A participant farming points by churning 100,000 units in and out of a low-liquidity perp market can be market-made profitably by anyone willing to sit on the other side and capture the spread.
	- Meme coins on new, technically difficult chains (poor wallets, broken block explorers, rudimentary DEX interfaces) generate outsized returns for early participants precisely because the friction deters sophisticated capital.
- ## Caveats & Edge Cases
	- Unsophisticated venues carry higher counterparty and operational risk: exchange solvency, smart contract vulnerabilities, and exit liquidity constraints are all elevated.
	- Unpredictable participants increase variance even when the expected value is positive. Size proportionately to account for wider outcome distributions.
	- Edges at inefficient venues compress quickly once they become well-known. The annoyance and obscurity that create the opportunity also define how long it lasts.
	- Venue risk is not uniform: some "drunk player" venues will not honour withdrawals or will intervene in profitable strategies. Assess counterparty trustworthiness before deploying meaningful capital.
