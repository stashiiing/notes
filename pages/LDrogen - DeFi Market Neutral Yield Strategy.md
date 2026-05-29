author:: [[ldrogen]]
summary:: Starkiller Capital runs a crypto market neutral strategy that generates yield by providing liquidity across DeFi protocols — lending, basis trades, carry trades, and market making — with returns uncorrelated to crypto price direction. The edge comes from rigorous diligence on protocol risk, access to pre-launch liquidity deals, and nimble reallocation between incentivised opportunities. The fund targets 15-20% net annual returns at a Sharpe of approximately 4, with capacity limited to around $100m.
category:: [[strategy]], [[framework]]
sub-cat:: [[quantitative]], [[arbitrage]], [[earn]]
timeframe:: [[position]], [[investing]]
market:: [[crypto]]
instrument:: [[spot]]
tools:: [[DeFi]], [[lending]], [[basis-trading]], [[carry]], [[liquidity-provision]], [[stablecoins]]
difficulty:: [[advanced]]
source:: https://youtu.be/eT4iZzJXCyA [00:01:06]
status:: [[draft]]

- {{video https://youtu.be/eT4iZzJXCyA}}
- # DeFi Market Neutral Yield Strategy
- ## TL;DR
	- A market neutral fund that earns yield across DeFi by providing liquidity to lending protocols, basis funds, carry trades, and market making strategies, sized by risk-adjusted yield scores. Returns are directionally uncorrelated to crypto beta but pro-cyclical in magnitude. The primary edge is diligence: identifying which high-yielding opportunities are worth the risk and which are not.
- ### Context
	- Most DeFi yield is available but dangerous. Protocols get hacked, depegged, or exploited constantly. The problem is not finding yield — it is finding yield that justifies the risk. A systematic framework that scores every opportunity and sizes accordingly allows participation in high-yield environments while limiting blowup exposure to manageable losses.
- ## Core Concept
	- The strategy treats DeFi yield the way a quant treats a factor model: enumerate all available opportunities, score each on a risk-adjusted basis, then size into them proportionally. No position should ever risk more than 1% of the book on a complete wipeout. Three sources of alpha exist in order of importance: diligence (risk management), access (pre-launch liquidity deals with token warrants), and nimbleness (reallocating quickly as incentives shift).
- ## Mechanics
	- 1. Build a universe of DeFi yield opportunities: lending vaults, basis funds, carry trades, market making, liquidity provisioning programmes.
	- 2. Score each opportunity on a risk-adjusted yield basis using both qualitative factors (team, code provenance, backers) and quantitative factors (source and sustainability of yield).
	- 3. Assign a probability of complete wipeout to each position.
	- 4. Size each position so the maximum expected loss is no more than 1% of the book.
	- 5. Target capacity of ~$100m to maintain 15-20% net / ~Sharpe 4 profile; larger AUM compresses returns toward 8-9% / Sharpe 2.
	- 6. Modulate overall risk exposure based on the general availability of yield across the ecosystem (see Pro-Cyclical Risk Allocation).
- ## Risk Management
	- No single position should be capable of losing more than 1% of the book on a complete wipeout.
	- Long-tail, high-yield positions (80-100% APR) are sized at 1% max.
	- High-quality, low-risk positions (e.g. basic Morpho USDC vault) can be sized up to near-full book concentration.
	- The risk curve is pulled in when ecosystem-wide risk-adjusted yield falls — preserving dry powder for dislocations (e.g. post-hack liquidity gaps yielding 17-18% on vanilla USDC lending).
- ## Examples
	- Superstate CME basis fund (USCC): long spot ETH/BTC/SOL staked for yield, short CME futures as hedge, producing 5-8% annually. Layered with Ripple's incentive on Aave Arcana to borrow rUSD against USCC at 2.5%, creating a meaningful leveraged spread.
	- Post-Kelp DAO hack: ecosystem yield had compressed, Starkiller was positioned conservatively. When the hack caused a liquidity gap, they stepped in to lend vanilla USDC/USDE on Aave at 17-18% APR for approximately one week.
- ## Caveats & Edge Cases
	- Strategy capacity is limited. At >$100m the book must move into lower-yielding, safer opportunities, compressing returns and Sharpe.
	- Returns are pro-cyclical in magnitude even if direction is uncorrelated: in a deep bear market with low ecosystem activity, monthly returns compress toward zero. A 2.5% net month in a down market is essentially impossible.
	- The strategy is not protected against correlated hacks or systemic DeFi failures.
	- Qualitative diligence on code provenance is a significant operational burden and difficult to scale without AI tooling.