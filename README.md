# Coin_Analysis
Top 200 Coins Analysis based on MarketCap

# Project Goal
This project aims to develop and optimize a cryptocurrency trading strategy using historical price data from the KuCoin exchange and market data from CoinMarketCap. The strategy focuses on identifying buy signals based on rapid price increases coupled with significant relative volume, with the goal of achieving profitable short-term trades.

# Logic and Implementation
1. Data Acquisition:
The code fetches historical price data (candlestick data) for cryptocurrency trading pairs (e.g., BTC-USDT) from the KuCoin API using the get_live_data function.
It retrieves circulating supply information for cryptocurrencies from the CoinMarketCap API using the get_circulating_supply function, which is cached for efficiency.
2. Strategy Logic:
The core trading logic resides in the run_backtest_live function.
It analyzes price data to identify buy signals based on three key criteria:
Price Increase: A significant percentage increase in price within a specified window_minutes.
Relative Volume: The current trading volume exceeding a threshold relative to the average volume over a recent period.
Circulating Supply: used to filter very low marketcap coins or tokens.
When a buy signal is detected, the code simulates a trade and tracks its outcome based on predefined profit (profit_target) and stop-loss (stop_loss) levels.
3. Automated Tuning:
The tune_strategy function automates the process of optimizing the strategy's parameters (e.g., price increase threshold, window minutes, volume threshold).
It iteratively tests different parameter combinations over a range of values, using the top 200 coins by market cap that are supported by Kucoin.
It seeks to maximize the success rate by prioritizing the conditions where the price increases by at least 5% before the price decreases by 2% and a take profit is reached before the stop loss.
The function then reports the best-performing parameters for each symbol and provides a visualization of the trades on a price chart.
4. Interactive Dashboard (Optional):
The code includes an interactive component using ipywidgets, allowing users to experiment with different parameter settings and visualize the strategy's performance in real-time.
# Key Features:
Automated Parameter Tuning: Optimizes strategy parameters to maximize profitability for the top 200 coins.
Relative Volume Filtering: Uses relative volume to identify potential breakout trades.
Profit and Stop-Loss Controls: Limits risk and ensures timely profit-taking.
Visualization: Provides charts to analyze and understand trade execution.
Flexibility: Adaptable for other trading pairs and data sources.

# Potential Applications:
Algorithmic Trading: Developing automated trading bots.
Backtesting Strategies: Evaluating the historical performance of trading rules.
Market Research: Identifying potential trading opportunities based on price action and volume patterns.
Educational Purposes: Learning and understanding cryptocurrency trading strategies.

# Disclaimer:
This code is intended for educational and research purposes only. It should not be used as a basis for making investment decisions without thorough evaluation and risk assessment. Cryptocurrency trading involves significant financial risk, and past performance is not indicative of future results.
