author:: [[ldrogen]]
summary:: Starkiller dynamically adjusts how far out on the risk curve they position based on the general availability of risk-adjusted yield across DeFi. When ecosystem yield is high, they extend into longer-tail positions. When yield compresses, they pull back to safer assets and preserve dry powder for dislocations. This makes monthly returns pro-cyclical in magnitude even though directionality is uncorrelated to crypto beta.
category:: [[framework]]
sub-cat:: [[quantitative]], [[earn]]
timeframe:: [[position]]
market:: [[crypto]]
instrument:: [[spot]]
tools:: [[DeFi]], [[position-sizing]], [[risk-management]], [[dry-powder]]
difficulty:: [[advanced]]
source:: https://youtu.be/eT4iZzJXCyA [00:21:39]
status:: [[draft]]

- {{video https://youtu.be/eT4iZzJXCyA?t=1299}}
- # Pro-Cyclical Risk Allocation
- ## TL;DR
	- When DeFi ecosystem yield is broadly high, Starkiller moves further out on the risk curve and takes on more long-tail exposure. When ecosystem yield compresses, they pull in that tail, sit in safer assets, and preserve dry powder. Returns are directionally uncorrelated to crypto price but pro-cyclical in magnitude: up-market periods produce higher monthly returns, down-market periods compress toward zero.
- ### Context
	- A static allocation to a fixed mix of safer and riskier DeFi positions would result in taking risk that isn't compensated in low-yield environments, and leaving alpha on the table in high-yield environments. Dynamic reallocation along the risk curve allows the fund to maintain a roughly constant risk-per-unit-of-expected-yield ratio across market cycles.
- ## Core Concept
	- The portfolio's position on the risk curve is a function of the aggregate risk-adjusted yield scores across the opportunity universe. When the full universe of scores rises (bull market, high activity, high incentives), the fund extends into longer-tail, higher-yielding positions. When the universe of scores falls, the fund contracts back toward the safe end. This is not market timing on price direction it is yield environment timing.
- ## Mechanics
	- 1. Monitor the aggregate risk-adjusted yield scores across all tracked DeFi opportunities continuously.
	- 2. When scores rise broadly (high ecosystem activity, bull market, active protocol incentives): extend position sizing into longer-tail, higher-APR opportunities.
	- 3. When scores fall broadly (compressed yields, low activity, risk-off): pull back to safer positions (e.g. vanilla USDC lending on audited protocols).
	- 4. Preserve dry powder in compressed environments to deploy rapidly into dislocations (e.g. post-hack liquidity gaps).
	- 5. Monthly return range: approximately 0 to 250 basis points, varying with how much risk is on the table.
- ## Examples
	- February-April period (referenced in interview): ecosystem yield compressed significantly, Twitter discussion about insufficient compensation for DeFi risk. Starkiller pulled into safer positions. The Kelp DAO hack then created a temporary liquidity vacuum. Starkiller deployed dry powder into Aave vanilla USDC/USDE lending at 17-18% APR for approximately one week.
- ## Caveats & Edge Cases
	- The strategy does not protect against tail events during high-risk periods it only ensures that when a blowup occurs it is in a 1% position, not a 10% position.
	- If the fund fails to modulate (i.e. holds long-tail exposure through a compressed yield environment), correlation to ecosystem beta increases materially.
	- Monthly returns approaching zero in bear markets are a feature of the design, not a failure the alternative is taking on uncompensated risk.