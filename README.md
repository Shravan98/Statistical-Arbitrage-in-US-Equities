# Statistical-Arbitrage-in-US-Equities
Independent study project on Statistical Arbitrage on US Equities

## Project Overview
This project replicates the statistical arbitrage strategy proposed by Marco Avellaneda and Jeong-Hyun Lee in their 2008 paper, Statistical Arbitrage in the U.S. Equities Market. The goal is to leverage stock-ETF pair relationships and identify cointegrated stock groups where price spreads exhibit mean-reverting behavior. Profits are generated by exploiting deviations from an equilibrium level through systematic trading signals, which revert to the mean.

## Authors
•	Niranjan Jahagirdar
•	Shravan Tummala
•	Ziyang Zeng

## Strategy Summary
## 1. Problem Statement
The strategy assumes stock prices are influenced by market factors, represented by ETFs. When a stock’s price deviates from its equilibrium level relative to its associated ETF, this “spread” can be modeled as a mean-reverting process, providing a basis for trades.

## 2. Key Concepts
•	Statistical Arbitrage: Exploiting price discrepancies in related assets.
•	Pairs Trading: Market-neutral approach that leverages deviations between correlated assets.
•	Co-integration: Identifying stable, long-term relationships between asset pairs to support pairs trading strategies.

## 3. Methodology
1 	ETF Approach: Sector ETFs are used as benchmarks to create a regression model for each stock's return, resulting in residuals analyzed for mean-reversion.
2.	PCA Approach: A principal component analysis decomposes returns into systematic factors, with residuals used to generate trade signals.
3.	Residual Analysis: Uses the Ornstein-Uhlenbeck (O-U) process to model residuals due to its mean-reverting characteristics.

## 4. Signal Generation
Trading signals are generated based on z-scores calculated from residuals:
•	Entry Thresholds:
o	Long position: Zt<−1.25Z_t < -1.25Zt<−1.25
o	Short position: Zt>1.25Z_t > 1.25Zt>1.25
•	Exit Thresholds:
o	Close long: Zt≥−0.5Z_t \geq -0.5Zt≥−0.5
o	Close short: Zt≤0.75Z_t \leq 0.75Zt≤0.75

## 5. Data and Preprocessing
•	Data Sources:
o	S&P 500 stocks
o	Sector ETFs
•	Cleaning Steps:
o	Mapped stocks to ETFs
o	Forward-filled missing data
o	Removed stocks with low liquidity or low correlation with ETFs

## 6. Results
Using the optimal thresholds, the strategy achieved:
•	Annual Return: 13.44%
•	Sharpe Ratio: 1.98
•	Max Drawdown: -6.6%
