# pairs-trading-backtester
Testing statistical arbitrage using cointegrated stock pairs

This notebook presents an interactive framework for simulating a quantitative pair trading strategy based on cointegration analysis and z-score thresholds. It leverages historical price data to identify statistically linked stock pairs, generate trading signals, and backtest performance over time. The interface is widget-driven for intuitive configuration and execution.

Strategy Overview

Pair trading is a market-neutral strategy that exploits price divergences between two historically correlated stocks. When their spread diverges significantly from its mean, the strategy enters a position expecting reversion to the long-term equilibrium.

Process
1. Cointegration Testing
   - Run an OLS regression:  
   - Apply the Augmented Dickey-Fuller (ADF) test to the residuals and to verify stationarity:
   - If the residuals are stationary, the stocks are cointegrated.

2. Z-Score Based Signal Generation
   - Compute the spread:  
   - Normalize to a z-score:
   - Trading logic:
     - Long spread when z_t < -1.5
     - Short spread when z_t > 1.5
     - Exit when |z_t| < 0.5

3. Backtesting and Capital Simulation
   - Simulate trades with dynamic capital updates.
   - Track position sizing, entry/exit timing, and realized profit.
   - Visualize cumulative PnL and individual trade performance.

 Features

- Interactive stock input via widgets
- Cointegration testing using ADF
- Spread and z-score visualization
- Strategy simulation with position sizing
- Cumulative profit tracking and trade table output
- Final performance plot over time


This dashboard is designed to help explore and refine market-neutral trading strategies in a reproducible, customizable format. It emphasizes statistical rigor, transparency, and modular logic for future expansion or automation.