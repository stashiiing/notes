- author:: [[LiquidityGoblin]]
  summary:: In HFT market making, edges degrade over time and signals stop working. A rigorous post-trade review loop examines both missed good trades and executed bad trades to continuously tighten the system. The goal is to increase the sample of winning trades while cutting losing ones before they compound.
  category:: [[framework]]
  sub-cat:: [[systematic]], [[algorithmic]], [[quantitative]]
  timeframe:: [[scalp]], [[intraday]]
  market:: [[crypto]], [[tradfi]]
  instrument:: [[spot]], [[perps]], [[futures]]
  tools:: [[Grafana]], [[Prometheus]]
  difficulty:: [[advanced]]
  source:: https://www.youtube.com/watch?v=wm1P8im1fuE&t=330s [05:30]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=wm1P8im1fuE&t=330s}}
- # Signal-Based HFT Post-Trade Review Loop
- ## TL;DR
	- HFT edges are fragile and time-sensitive. A structured post-trade review identifies why good trades were missed and why bad trades were taken, then closes that loop through parameter adjustment. The review asks: are our signals still working, and are we still able to act on them?
- ### Context
	- In high-frequency trading, the market continuously becomes more efficient as other participants discover and trade the same signals. A static system degrades without active review. The post-trade loop is the mechanism that keeps a system profitable by surfacing where it is leaving money on the table or bleeding on stale edges.
- ## Core Concept
	- Trading is driven by signals — observable events that predict a price move over a short horizon. The review loop examines every trade and non-trade against those signals to determine whether the system behaved correctly. Over time, signals weaken and must be combined, filtered, or retired.
- ## Mechanics
	- Identify a leading venue where price discovery occurs (e.g. Binance for BTC/USDT).
	- Define a signal: a discrete event on the leading venue, such as a large trade or a tick move, that historically predicts a directional move on a lagging venue.
	- Co-locate or minimise latency to the lagging venue to act within the propagation window.
	- After each session, review two categories of outcome: trades that should have been taken but were not, and trades that were taken but should not have been.
	- For missed trades, diagnose whether the cause was latency, competitor priority, or a parameter threshold set too conservatively.
	- For bad trades, check whether the signal has weakened. If a trigger that historically produced a 20 basis point move is now producing 5 basis points, or not covering transaction costs, the signal requires adjustment or retirement.
	- Combine weakened signals with complementary ones to reconstruct a viable edge rather than discarding them outright.
	- Adjust parameters daily or weekly; a system left untouched for two to three weeks will stop producing alpha.
- ## Entry / Trigger
	- A qualifying event on the leading venue within the latency window of the lagging venue. The threshold (e.g. a trade above a dollar size, a tick of a given magnitude) is defined in advance and reviewed continuously against realised outcomes.
- ## Risk Management
	- Monitor trade rate as a proxy for system health; a sudden spike or a multi-minute silence both warrant investigation.
	- Use alerting infrastructure (e.g. Grafana IRM, Prometheus alert manager) to surface anomalies without requiring constant manual attention.
	- Recognise that variance in outcomes on any single signal is expected; the edge is expressed over sample size, not individual trades. Winning 51% of trades at scale is sufficient; do not over-optimise for individual trade outcomes.
- ## Examples
	- A trigger fires on every Binance trade above $50,000, historically predicting a 20 basis point move on a tier-two exchange within the next minute. Over a week, those trades produce only 5 basis points on average and no longer cover round-trip transaction costs. The signal is flagged for review: either the threshold is raised, the signal is combined with a second confirming signal, or the trigger is retired.
	- A team sends orders to a lagging venue simultaneously with competitors. Network jitter means competitors sometimes land first. Post-trade review surfaces the pattern; the team investigates co-location improvements or order prioritisation rather than assuming the signal is dead.
- ## Caveats & Edge Cases
	- Some missed trades are correctly missed: network jitter and competitor priority are structural, not fixable through parameter tuning alone.
	- Signals can weaken gradually rather than switching off sharply, making degradation easy to miss without a disciplined review cadence.
	- Over-tuning parameters to recent data introduces curve-fitting; the review loop should distinguish between a structural change in the signal and short-term noise.
	- Manual input remains necessary even with a largely automated system; the system is a high-dimensional control problem that cannot be fully solved algorithmically.
