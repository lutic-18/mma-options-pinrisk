# A-simple-pin-risk-analysis-for-options-using-python
This project explores pin risk in options, focusing on how close-to-close price movements affect whether contracts expire in- or out-of-the-money. The analysis is based on intraday 5-minute data for major tickers (SPY, QQQ, AAPL, TSLA, etc.), with special attention to 0DTE options (SPY/QQQ) versus other single-stock options.

## Data Source
- 5-minute OHLCV data for SPY, QQQ, and selected US stocks
- Historical intraday prices (April–July 2025 sample)
- Synthetic aggregation of T-90, T-60, T-30, T-5 minute snapshots before close

## Methodology
1. Extracted intraday levels (T-90, T-60, T-30, T-5, Close) for each date and ticker.
2. Calculated absolute and relative changes between intraday levels and daily close.
3. Built ECDF plots to visualize distribution of price deviations.
4. Analyzed percentiles (p50, p90, p95, p99) to determine thresholds of significant movements.
5. Compared 0DTE underlyings (SPY, QQQ) with broader set of MMA tickers.

## Tech Stack
Python (pandas, numpy, matplotlib)
Jupyter Notebook (EDA, visualization, analysis)

## Future Enhancements
- Extend dataset to longer history for more robust statistics.
- Add volatility clustering and ATR-based thresholds.
- Simulate option payoff scenarios given observed price moves.
- Automate heatmap + ECDF reporting for new tickers.

## Conclusion

This project demonstrates how intraday price data can be used to quantify pin risk for options near expiration.
- For SPY/QQQ (0DTE): significant movements rarely occur after T-30; by T-5 the price is almost fixed.
- For other MMA tickers: most stabilize by T-30, but volatile names (NFLX, META, TSLA) show large swings even near the close.
  
The repository serves as a foundation for systematic risk management rules in options trading — e.g., deciding when to force-close positions to minimize unexpected assignment risk.
