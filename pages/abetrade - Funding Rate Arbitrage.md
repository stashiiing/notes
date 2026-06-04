- author:: [[abetrade]]
  summary:: Funding rate arbitrage is the perpetual future equivalent of a cash-and-carry trade. When funding is positive, a trader buys spot and shorts the perpetual in equal size to achieve delta neutrality and collect the funding payments made by longs. The same logic applies cross-exchange when funding differs significantly between venues. The trade is not risk-free: funding can flip, the short leg requires margin, and exit slippage on thin venues can exceed weeks of collected carry.
  category:: [[strategy]]
  sub-cat:: [[arbitrage]], [[earn]]
  timeframe:: [[swing]], [[position]]
  market:: [[crypto]]
  instrument:: [[perps]], [[spot]]
  tools:: [[funding rate]]
  difficulty:: [[advanced]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Funding Rate Arbitrage
- ## TL;DR
	- When perpetual funding is positive, longs pay shorts on a recurring basis. A trader who buys spot and shorts the perpetual in equal notional size is delta neutral and collects that funding at each interval. The trade scales: at 0.05% per eight hours (roughly 55% annualised), the yield is meaningful on a position with no directional exposure. Cross-exchange, the same coin can carry wildly different funding on different venues, opening a further spread to harvest. The edge is real but so are the risks: funding can flip, the short leg needs margin and can be liquidated, and unwinding size on thin venues can cost more in slippage than weeks of collected carry.
- ### Context
	- Funding rate arbitrage is the main delta-neutral strategy tied to perpetuals in crypto. It explains why extreme funding blowoffs are rarer now than in earlier years: large amounts of capital are positioned to harvest them. Understanding it also explains much of the structural negative funding observed in altcoins, as market makers hedge spot inventory by shorting perps.
- ## Core Concept
	- The trade is the perp equivalent of the classical cash-and-carry arbitrage used in dated futures, where a trader buys spot and shorts a premium-priced dated contract, collecting the basis as it converges at expiry. In perpetuals there is no expiry, so instead of a one-time convergence the trader collects recurring funding payments.

	  Delta neutrality: long spot and short perp in equal notional size. A 1% rise in price makes the spot leg gain 1% and the perp leg lose 1%. Net directional exposure is approximately zero. What remains is the funding yield.

	  Cross-exchange extension: when the same coin carries a high funding rate on one exchange and a low or negative rate on another, a trader goes long the cheap perp and short the rich one, staying delta neutral and collecting the spread between the two rates.
- ## Mechanics
	- Buy X notional of spot. Short X notional of the perpetual on the same coin.
	- At each funding interval, collect the payment made by longs (when funding is positive).
	- Example: Long 10 ETH spot, short 10 ETH perp at 0.05% per eight hours. Net delta is zero. Weekly yield is approximately 1.05% on the position.
	- Cross-exchange variant: long the perp on the low-funding venue, short the perp on the high-funding venue. No spot leg required, but counterparty risk is split across two exchanges.
	- The opposite case (deeply negative funding) means shorts pay longs. The mirror trade is to short spot and go long the perp, collecting the carry from the short side.
- ## Risk Management
	- Funding can flip mid-trade, putting the trader on the paying side. Monitor the rate and be prepared to exit quickly.
	- The short perp leg requires margin. A fast price spike makes the spot leg gain but also temporarily requires topping up margin on the short leg. If the legs are on different venues, transfer delays can cause the short to be liquidated even though the overall position is hedged.
	- Unwinding size on a thin venue mid-move can cost more in slippage than weeks of collected funding. Size the position to allow a clean exit.
	- Cross-exchange positions carry counterparty risk on every platform touched and split capital inefficiently.
- ## Caveats & Edge Cases
	- Funding arbitrage works until it does not. It is a risk premium, not genuinely risk-free yield.
	- The strategy's own success compresses its returns: large amounts of capital now sit ready to harvest funding spikes, which is why extreme rates are shorter-lived and less extreme than they were in earlier crypto market cycles.
	- Deeply negative altcoin funding sounds attractive (the market is paying you to be long) but the directional risk of an 80% drawdown in the token typically overwhelms the funding income. The trade requires careful sizing and a view on the token's downside risk.
