- author:: [[LiquidityGoblin]]
  summary:: Risk in trading is multi-dimensional and extends well beyond position size and volatility. Counterparty, operational, and security risks are fat-tailed and largely unquantifiable but highly mitigable through diversification, layered security practices, and proportionate sizing. The framework treats risk as something to be massaged around rather than solved.
  category:: [[framework]]
  sub-cat:: [[philosophy]], [[systematic]]
  timeframe:: 
  market:: [[all]]
  instrument:: 
  tools:: [[Grafana IRM]], [[PagerDuty]], [[hardware wallet]]
  difficulty:: [[intermediate]]
  source:: https://www.youtube.com/watch?v=wm1P8im1fuE&t=3108s [51:48]
  status:: [[draft]]
- {{video https://www.youtube.com/watch?v=wm1P8im1fuE&t=3108s}}
- # Operational and Counterparty Risk Mitigation Framework
- ## TL;DR
	- Beyond position-level risk (size and volatility), traders face counterparty risk (exchange insolvency), operational risk (code failures, stale orders), and security risk (hacks, SIM swaps). These tail risks are not precisely measurable but are highly manageable through diversification, alerting infrastructure, and basic security hygiene. Risk is never binary; the goal is proportionate mitigation, not elimination.
- ### Context
	- FTX demonstrated that counterparty risk in crypto is a genuine fat tail: portfolios concentrated on a single venue can go to zero overnight through no fault of the trader's own strategy. Similarly, a code bug that leaves hundreds of stale orders open, or a compromised hot wallet, can cause losses that dwarf any single bad trade. These risks are structurally different from market risk and require different mitigations.
- ## Core Concept
	- Risk has multiple independent dimensions. Each dimension requires its own mitigation approach. The engineering framework of likelihood times severity, addressed by the lowest-effort controls first, provides a practical structure for identifying and implementing mitigations without over-engineering.
- ## Mechanics
	- **Counterparty risk**: Spread capital across multiple exchanges and venues. No single venue should hold a concentration that would be catastrophic if it failed. Treat exchange balances as unsecured credit exposure.
	- **Operational risk (code and order management)**: Implement real-time alerting on trade rate (spike or silence), data feed latency, and position size thresholds. Use Prometheus with Grafana alert manager or Grafana IRM (free for up to two to three users) as an alternative to PagerDuty. Configure call escalation so alerts persist until acknowledged. Have a manual fallback (e.g. a trading terminal) to cancel stale orders if automated systems fail.
	- **Security risk**: Use hardware wallets for meaningful balances. Store at least one hardware wallet off-site so a physical breach does not result in total loss. Separate hot wallets from cold wallets by function and keep hot wallet balances minimal.
	- **Honeypot wallet**: Maintain a hot wallet on the primary machine with a small but meaningful balance (e.g. $1,000) and configure an alert on any outbound transaction. If this wallet is drained, it signals that the machine is compromised and triggers an immediate response: wipe the machine, move cold wallet assets to new addresses. The cost is the honeypot balance; the benefit is early detection before larger holdings are exposed.
	- **Sizing for tail risk**: Allocate to high-risk or untrustworthy venues in proportion to the probability-weighted loss, not the expected return. A $200 position on a venue with a meaningful chance of non-delivery may still be worthwhile if the upside is $1,000, but a $20,000 position on the same venue is not.
- ## Examples
	- FTX collapse: traders with capital concentrated on FTX lost everything regardless of strategy quality. The mitigation is venue diversification, implemented before a failure event, not after.
	- Code failure scenario: a system bug causes hundreds of orders to remain open on an exchange that does not support cancel-on-disconnect. Without a manual fallback, those orders execute against adverse flow. With a terminal and a cancel-all function accessible, the trader can intervene within minutes.
	- Hardware wallet off-site: if a trader's home is burgled, a hardware wallet stored elsewhere means the loss is limited to the hot wallet balance rather than the full portfolio.
	- Honeypot wallet: a $1,000 hot wallet with an alert fires at 3 a.m. The trader wakes, confirms the machine is compromised, wipes the laptop, and migrates cold wallet assets before the attacker can access the hardware wallet. The $1,000 loss prevents a much larger one.
- ## Caveats & Edge Cases
	- Diversification across venues introduces capital inefficiency: funds spread thin cannot be deployed optimally on any single venue.
	- Alert fatigue is a genuine failure mode. Calibrate alert thresholds carefully so that genuine emergencies are not buried in noise.
	- The honeypot wallet approach assumes an attacker will drain the most accessible wallet first. A targeted, sophisticated attacker may not follow this pattern.
	- Security hygiene measures (hardware wallets, off-site storage, SIM swap prevention via carrier PIN locks) have upfront friction costs that deter implementation. The asymmetry of potential loss versus the cost of implementation strongly favours early adoption.
