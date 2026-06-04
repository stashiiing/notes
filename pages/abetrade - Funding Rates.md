- author:: [[abetrade]]
  summary:: The funding rate is the mechanism that keeps a perpetual future anchored to spot price. It is a recurring payment exchanged between longs and shorts at fixed intervals, composed of a fixed interest rate and a premium index reflecting the contract's deviation from spot. The rate is a direct sentiment gauge and one of the primary inputs for reading positioning in crypto.
  category:: [[concept]]
  sub-cat:: [[orderflow]], [[quantitative]]
  timeframe::
  market:: [[crypto]]
  instrument:: [[perps]]
  tools:: [[funding rate]]
  difficulty:: [[intermediate]]
  source:: https://blog.tradingriot.com/p/how-to-trade-cryptocurrencies
  status:: [[draft]]
- {{video }}
- # Funding Rates
- ## TL;DR
	- Funding is a payment exchanged directly between long and short holders at fixed intervals (every eight hours by default on most exchanges). The exchange takes no cut and only moves the payment from one side to the other. The rate has two components: a fixed interest rate set by the exchange and a premium index measuring how far the contract is trading from spot. Together they create a structural positive bias in most markets and a real-time sentiment gauge.
- ### Context
	- Without expiry to force convergence, perpetuals need a mechanism to stay anchored to spot. Funding is that mechanism. It also encodes market sentiment in a measurable, real-time signal, making it one of the most useful inputs for building a view on positioning.
- ## Core Concept
	- Funding Rate = Interest Rate + Premium Index

	  The interest rate is fixed by the exchange (Binance sets 0.01% per eight-hour interval for most USDT contracts, roughly 10.95% annualised). The premium index measures the gap between the perpetual and spot, computed from impact bid and ask prices time-weighted across the interval. A clamp limits how much the premium can swing the final rate.

	  When the perpetual is trading at or near spot, the premium washes out and funding settles at the flat interest rate. Only when the premium pushes outside a narrow band does funding begin tracking the premium itself.

	  Positive funding means longs pay shorts. Negative funding means shorts pay longs. Because the interest rate component creates a structural positive tilt, even a perfectly balanced market has longs paying a small amount.
- ## Mechanics
	- Settlement occurs at fixed timestamps (Binance: 00:00, 08:00, 16:00 UTC). You only pay or receive if you hold a position at the settlement timestamp.
	- Payment applies to notional, not margin: Funding Payment = (Mark Price × Position Size) × Funding Rate.
	- Example: Long 10 BTC at 0.01% funding pays 0.001 BTC to shorts per interval.
	- The clamp (approximately ±0.05%) keeps a single dislocation from blowing the rate out. Once the premium sits within the band, the adjustment term collapses and only the interest rate applies.
	- Exchanges cap the final rate (Binance bounds most majors at ±0.75% of maintenance margin ratio) and switch to hourly settlement when the cap is pinned.
	- Some contracts (ETHBTC and certain altcoins) carry a 0% interest rate, removing the structural positive tilt.
- ## Caveats & Edge Cases
	- Funding encodes positioning and sentiment but is a lagging confirmation, not a leading signal on its own. It is most useful as confluence with open interest and price action.
	- Extreme positive funding (hundreds to thousands of percent annualised) can appear on illiquid altcoins and is not necessarily sustainable or exploitable without significant execution risk.
	- Funding can flip mid-trade. A funding arbitrage position that starts collecting positive carry can reverse and put the trader on the paying side.
