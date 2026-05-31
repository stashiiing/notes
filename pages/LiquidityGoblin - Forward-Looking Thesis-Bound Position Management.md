- author:: [[LiquidityGoblin]]
  summary:: Every trade should be defined by a specific price forecast and a specific time horizon before entry. Position decisions — whether to add, hold, reduce, or exit — are made by re-evaluating the forward thesis at each point in time, not by reference to entry price or unrealised P&L. Sunk cost and anchoring to prior prices are the primary causes of avoidable losses.
  category:: [[philosophy]]
  sub-cat:: [[discretionary]], [[philosophy]]
  timeframe:: 
  market:: [[all]]
  instrument:: 
  tools:: 
  difficulty:: [[beginner]]
  source:: https://www.youtube.com/watch?v=wm1P8im1fuE&t=1027s [17:07]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=wm1P8im1fuE&t=1027s}}
- # Forward-Looking Thesis-Bound Position Management
- ## TL;DR
	- Define a price target and time horizon before entering any trade. Manage the position by continuously re-asking: given where we are now, what is my forward forecast? If the thesis has not played out by the horizon, exit. Decisions based on entry price, unrealised loss, or hope of reversal destroy edge over time.
- ### Context
	- Most retail traders implicitly hold positions based on where they entered rather than where they expect the market to go. This produces two common failure modes: holding losers past the point where the thesis has expired, and holding winners past the point where the edge has been realised. Applying a quantitative framing to even manual, discretionary trades corrects both biases.
- ## Core Concept
	- A trade is a time-bounded forecast. If the forecast does not materialise within the specified horizon, the trade has failed regardless of unrealised P&L. The correct question at any moment is not "am I up or down?" but "if I had no position, would I enter this trade right now at the current price?" If the answer is no, exit.
- ## Mechanics
	- Before entering a position, explicitly define two parameters:
		- **Price target**: where you think the asset will trade, and why (e.g. ETH/BTC correlation expected to strengthen from 86% to 90%, implying a specific ETH price).
		- **Time horizon**: the period over which the thesis is expected to play out (e.g. 2 weeks, 1 day, 5 seconds in HFT context).
	- During the trade, evaluate the position on a forward-looking basis only. Ask: has the thesis changed? Is the original catalyst still in play? Is the horizon still appropriate?
	- If the horizon passes without the thesis realising, exit. Do not extend the horizon retroactively to accommodate an unchanged position.
	- If a better opportunity with higher expected value (net of exit transaction costs) presents itself, switch. Capital should always be allocated to the highest forward expected value use, not to recovering a prior entry price.
	- Apply this framework across all active positions simultaneously. Periodically ask: if I had no positions, what are the best 10 trades I could put on right now? If any of those have higher expected value than a current holding, the holding should be replaced.
- ## Examples
	- A thesis that the Ethereum Foundation will sell ETH over the next 2 weeks is a 14-day forecast. If 14 days pass without the expected move, the thesis has expired. The correct action is to exit and reassess, not to extend the holding period because the position is offside.
	- A correlation model predicts ETH should trade at $3,100 given current BTC price and an expected 90% correlation. If ETH trades above $3,100, the model suggests no long edge; if below, a long is warranted. The position is managed by updating the model continuously, not by where ETH was when the trade was entered.
	- An HFT signal predicts a 20 basis point move within 1 minute of a trigger event. If the move does not occur within that minute, the signal has not realised. The position is exited on the horizon, not held in expectation of a delayed move.
- ## Caveats & Edge Cases
	- This framework requires that the trade thesis is explicit and measurable before entry. Vague theses ("I think ETH will go up") cannot be evaluated or invalidated against a horizon, which is itself a failure mode.
	- Frequent re-evaluation increases transaction costs in assets with wide spreads or high fees. Account for this when setting minimum holding horizons.
	- The framework does not prescribe a specific horizon length; that depends on the strategy. The requirement is that the horizon is defined in advance and adhered to.
	- Conviction can legitimately change before the horizon expires if new information arrives that materially alters the thesis. Distinguish between updating on new information (valid) and capitulating on noise (invalid).
