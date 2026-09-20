# Statistical-Pairs-Trading-Backtester-in-Python

The backtesting strategy covers the complete quantitative research pipeline: pulling historical price data via yfinance, computing a hedge ratio through linear regression to establish the price relationship between the two stocks, and constructing a spread that captures their relative valuation gap.

This spread is normalized into a rolling Z-score, which drives the core trading signal — entering offsetting long/short positions when the Z-score crosses ±2 standard deviations from its 20-day average, and exiting once the relationship reverts toward the mean.

I built a full day-by-day backtest engine from scratch, tracking daily and cumulative P&L based on position and spread changes while explicitly avoiding look-ahead bias.

To make the backtest realistic, I incorporated transaction cost modeling (0.05% per trade), comparing gross versus net performance to quantify how much trading friction erodes returns over an 11-year period.

I then evaluated the strategy using risk-adjusted performance metrics — Sharpe ratio, maximum drawdown, trade count, and win rate — rather than relying on a rising equity curve alone.

The results showed that the strategy was net profitable over the long run, but with a modest Sharpe ratio (~0.21) and a meaningful drawdown (~37% of peak profit), highlighting that consistent profitability doesn't always mean strong risk-adjusted performance — a key lesson in quantitative finance.
