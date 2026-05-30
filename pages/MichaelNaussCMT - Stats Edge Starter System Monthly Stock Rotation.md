- author:: [[MichaelNaussCMT]]
  summary:: A monthly stock-rotation system that selects the five most short-term oversold stocks from the Russell 3000 that are in established uptrends, subject to a broader market regime gate. It holds equal-weight positions for one month, exits to cash when the regime turns bearish, and has produced a 13.58% CAGR over a 26-year backtest versus 8.44% for buy-and-hold SPY.
  category:: [[strategy]]
  sub-cat:: [[systematic]], [[quantitative]]
  timeframe:: [[position]]
  market:: [[equities]]
  instrument:: [[spot]]
  tools:: [[RSI]], [[moving-average]], [[stock-screener]], [[Russell-3000]]
  difficulty:: [[intermediate]]
  source:: https://letters.statsedgetrading.com
  status:: [[draft]]
- # Stats Edge Starter System Monthly Stock Rotation
- ## TL;DR
	- A fully rules-based monthly rotation system that buys the five most beaten-down stocks inside established uptrends when the S&P 500 regime is healthy. Equal-weight, no leverage, no options. Run once a month on the last trading day; hold for one month; exit to cash when the regime turns off. Backtested 26 years at 13.58% CAGR with a worst drawdown of 26.28%, versus 8.44% CAGR and 46.49% drawdown for buy-and-hold SPY.
- ### Context
	- Most retail traders fail to hold beaten-down positions in good stocks because short-term price decline triggers a sell response rather than a buy. A rules-based system removes that emotional response and instead systematically exploits the well-documented tendency for short-term oversold conditions within longer-term uptrends to revert upwards. The regime filter prevents buying dips in genuinely deteriorating markets, which is where mean-reversion strategies historically break down.
- ## Core Concept
	- Buy the five most short-term oversold stocks in the Russell 3000 that are still in long-term uptrends, but only when the broader market is itself in a healthy regime. Step aside entirely into cash when the regime breaks. Repeat at every month-end.
- ## Mechanics
	- Universe: Russell 3000 using historical constituency at each rebalance date (survivorship-bias-free).
	- Cadence: once a month, on the last trading day.
	- Screen: retain only stocks where all four conditions are simultaneously true.
		- Stock price is above its 12-month moving average (long-term uptrend confirmation).
		- Stock price is greater than $5 (penny stock exclusion).
		- Three-month average daily volume exceeds 1,000,000 shares (liquidity filter).
		- S&P 500 four-period RSI is greater than 50 (regime gate).
	- If the regime condition fails, no new positions open and any existing positions close immediately. Capital sits in cash until the regime recovers.
	- Selection: of stocks passing the screen, rank by two-period RSI ascending; select the five with the lowest RSI(2).
	- Sizing: 20% of investing capital per position; five positions; fully invested when the regime is on.
	- Entry: buy at the next monthly open after the screen runs.
	- Hold period: one month.
	- Exit: sell all five at the following month-end and re-run the screen. Mid-month early exit if the S&P 500 RSI(4) falls to 50 or below, or if any individual stock drops back below its 12-month moving average.
- ## Entry / Trigger
	- Screen runs on the last trading day of the month. Entry orders are placed at the open of the following month. The trigger is the completion of the monthly screen with at least one stock passing all four filter conditions.
- ## Risk Management
	- Position sizing is fixed at 20% per stock across five positions; there is no leverage. Mid-month stop conditions are an S&P 500 RSI(4) reading of 50 or below, or an individual stock closing below its 12-month moving average. No position-level stop-loss beyond these rules; the regime filter and trend filter act as the primary risk controls. The worst backtested peak-to-trough drawdown across 26 years was 26.28%.
- ## Examples
	- Over 26 years from February 2000 through May 2026, the system executed 1,090 trades averaging approximately 42 per year. The win rate was 56.51% with a profit factor of 1.38. Average winning trades returned +8.70%; average losing trades cost 7.53%. Average time invested in the market was 73.9%, with the remainder in cash during bearish regime periods. The $100,000 starting stake compounded to $2,226,226 versus $844,414 for buy-and-hold SPY over the same period.
- ## Caveats & Edge Cases
	- Historical constituency data for the Russell 3000 is required; using the current index composition introduces survivorship bias that inflates backtest results. Free screeners typically cannot apply all four filters simultaneously; paid tools such as TradingView Pro or dedicated backtesting platforms with Norgate data are needed. Missing even one monthly rebalance materially changes the system being run. The discipline to follow picks during drawdowns, when selected stocks will often look broken and carry negative news flow, is the primary execution risk. The system is unsuitable for very large portfolios where liquidity across five Russell 3000 names becomes a constraint. Backtested results are not a forecast; future drawdowns may exceed the historical worst of 26.28%.
