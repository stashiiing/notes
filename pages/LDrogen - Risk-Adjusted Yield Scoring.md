author:: [[ldrogen]]
summary:: Starkiller Capital scores every DeFi yield opportunity on a combined qualitative and quantitative basis to produce a risk-adjusted yield score. The qualitative side assesses team reputation and code provenance; the quantitative side focuses entirely on understanding the source and sustainability of the yield. This score drives position sizing.
category:: [[framework]]
sub-cat:: [[quantitative]], [[earn]]
timeframe::
market:: [[crypto]]
instrument:: [[spot]]
tools:: [[DeFi]], [[lending]], [[risk-scoring]], [[position-sizing]]
difficulty:: [[advanced]]
source:: https://youtu.be/eT4iZzJXCyA [00:03:04]
status:: [[draft]]

- {{video https://youtu.be/eT4iZzJXCyA?t=184}}
- # Risk-Adjusted Yield Scoring
- ## TL;DR
	- Each DeFi yield opportunity is assigned a risk-adjusted yield score based on qualitative assessment of team and code provenance, plus quantitative analysis of where the yield actually comes from and how sustainable it is. The score determines position sizing, with a hard rule that no position should risk more than 1% of book on full wipeout.
- ### Context
	- DeFi offers a wide range of yield opportunities with wildly different risk profiles. Without a systematic scoring framework, the tendency is to either over-concentrate in high-yielding positions (dangerous) or underweight them out of fear (leaves alpha on the table). The scoring system allows the fund to treat the full opportunity set as an efficient frontier and position along it rationally.
- ## Core Concept
	- The primary risk in DeFi yield is hacking risk: will the protocol get exploited? The qualitative layer assesses how likely that is. The quantitative layer assesses whether the yield makes sense economically. Yield that cannot be explained is the single biggest red flag — "there are no magic money trees." If you cannot trace the source of the yield, you are likely taking on hidden tail risk.
- ## Mechanics
	- **Qualitative factors:**
		- Reputation and track record of the founding team.
		- Code provenance: is the codebase a fork of audited, battle-tested protocols or novel untested code? Protocols that get hacked often share code lineage with previously hacked protocols.
		- Quality of backers: large VCs or institutional trading firms are more likely to backstop losses in a hack (as has happened with several major bridge exploits).
	- **Quantitative factors:**
		- Identify the exact source of the yield. Is it real fee revenue, protocol incentives paid in a governance token, an unsustainable reward schedule, or an arbitrage spread?
		- Assess sustainability: governance token rewards at inflated valuations are a valid but temporary source; real fee revenue is more durable.
		- Model the utilisation dynamics of lending markets: at what utilisation rate does the spread close, and what is the probability of that happening?
		- Estimate the expected yield over the holding period given all of the above.
	- **Output:** a risk-adjusted yield score per opportunity, used to construct the portfolio along an efficient frontier.
- ## Examples
	- In 2020-2021, 1,000% APR farms existed. The source was governance token emissions at inflated valuations. The yield source was identifiable and real but clearly unsustainable — useful to participate in briefly, not to hold.
	- The Superstate/rUSD carry trade: Ripple incentivises rUSD borrowing against USCC. Source of yield is Ripple's strategic spend to grow rUSD market cap. Sustainability depends on Ripple's continued incentive programme and lending market utilisation dynamics.
- ## Caveats & Edge Cases
	- Qualitative diligence on code provenance is non-trivial and time-intensive; AI tooling is used to scale this across the full DeFi landscape.
	- Even thorough diligence will eventually produce a blowup — the framework assumes this and limits it to a 1% loss rather than attempting to prevent it entirely.
	- Backers filling holes post-hack is not guaranteed; this qualitative factor is probabilistic, not a certainty.