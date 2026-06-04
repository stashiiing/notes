author:: [[GoshawkTrades]]
summary:: A process for sourcing and evaluating new strategy ideas centred on understanding the underlying reason an edge exists rather than pattern-matching on historical data. Ideas come from books, Twitter, research papers and gaps in the existing portfolio. The filtering question is always: can I articulate why this should make money in the future?
category:: [[framework]]
sub-cat:: [[systematic]], [[algorithmic]], [[philosophy]]
timeframe::
market:: [[all]]
instrument::
tools:: [[backtesting]], [[research]]
difficulty:: [[intermediate]]
source:: https://www.youtube.com/watch?v= [19:10]
status:: [[draft]]

- # Strategy Idea Generation and Filtering
- ## TL;DR
	- A strategy idea is only worth testing if you can articulate why it should make money — not just that it has in the past. Source ideas from books, Twitter, research papers and your portfolio's correlation gaps. Apply a prior filter before any backtesting: does this idea have a credible economic reason to generate returns? Discard quickly if not.
- ### Context
	- Early in his career Minir tested almost every idea he encountered. After seven years he now filters roughly four or five ideas before testing one, and finds genuinely new ideas increasingly rare. The key shift was moving from pattern recognition to first-principles reasoning about why an edge would persist.
- ## Core Concept
	- Most durable trading edges are risk premiums: they exist because an asset is riskier than alternatives, because a market is less accessible than it should be, or because a structural imbalance creates a persistent opportunity (e.g. arbitrage). If you can identify the underlying reason, you have a reason to believe the edge will persist on future data. If you can only say "it worked historically," you probably have curve-fit noise.
- ## Mechanics
	- Maintain a continuous idea backlog from three sources: books (Robert Carver's Advanced Futures Strategies is recommended), Twitter and research papers.
	- When portfolio correlation analysis reveals over-concentration in a strategy type, target idea generation specifically for what is missing (e.g. if 70% is trend-following, look explicitly for mean-reversion or arb ideas).
	- Apply the prior filter before writing any code: "Can I explain in one or two sentences why this edge exists and why it will continue to exist?"
	- If yes: backtest on in-sample data, then validate on out-of-sample data.
	- If no, or if the only answer is "it looked good in the chart": discard without testing.
	- Treat the hit rate honestly. Early on, expect roughly 1 in 12 ideas to show promise. With experience, this may improve to 1 in 5 or 1 in 6, but genuinely new ideas become rarer.
	- Follow the scientific method: hypothesis, test, evaluate, decide — do not iterate indefinitely on a failing idea.
- ## Examples
	- Korean stocks becoming accessible on Interactive Brokers due to AI sector interest: a clear structural reason (previously mispriced due to access barriers) that justified investigating a long-biased strategy.
	- Arbitrage between two venues: even a child can explain why you make money buying cheap and selling dear, so the prior filter is trivially satisfied.
- ## Caveats & Edge Cases
	- The prior filter is necessary but not sufficient. A credible reason for an edge does not guarantee the edge is large enough to trade after costs, or that your specific implementation captures it.
	- Twitter is a high-signal source but also high-noise. Curate carefully and verify ideas independently before testing.
	- Once you have roughly 10 strategies, finding genuinely uncorrelated new additions becomes very difficult. Most of your time will shift from idea generation to portfolio maintenance and incremental optimisation.