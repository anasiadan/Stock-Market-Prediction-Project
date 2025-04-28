# 1.Overview
The goal of this project is  to predict next-day stock direction (Up/Down) using technical indicators.

# 2.Process
### EDA Insights Summary
The exploratory data analysis of the stock market dataset revealed several important patterns. The closing price trends show that most technology stocks, including Apple, Amazon, Microsoft, Google, and NVIDIA, have followed a strong long-term upward trajectory, with notable events like the COVID-19 market dip clearly visible. Correlation analysis indicated that these stocks are highly positively correlated, moving largely in the same direction, which suggests that sector or market-wide dynamics play a major role. Volume analysis revealed that trading activity spikes sharply during periods of market volatility, making volume a potentially powerful feature for predicting unusual market behavior. Moving average plots demonstrated how smoothing techniques can highlight underlying trends and possible trend reversals, offering opportunities for feature engineering using crossover signals. Finally, volatility analysis showed that while most trading days are relatively stable, there are occasional extreme spikes, typically during market shocks, that could be important for modeling risk.

Based on these insights, the following actionable steps are recommended:
- Create lag features using past stock prices and returns to capture momentum and trend patterns.
- Engineer volume-based features, such as volume spikes relative to historical averages, to detect periods of unusual activity.
- Use moving average crossovers (e.g., 50-day vs 200-day) as signals for trend reversals or continuation patterns.
- Incorporate cross-stock relationships by using features from multiple stocks, given their high correlation.
- Model volatility explicitly by creating features that capture large intraday price movements or sudden changes in trading volume.
- Consider sector-wide indicators (like tech sector ETFs) to enhance predictions based on broader market behavior.

# 3.Tools and methods used

# 4.Data
- The data of this project is open source historical stock market data of five major Big Tech companies: NVIDIA (NVDA), Apple (AAPL), Microsoft (MSFT), Google (GOOGL), and Amazon (AMZN) over a 15 years from January 1, 2010 to January 1, 2025. Data source can be found in [Kaggle](https://www.kaggle.com/datasets/marianadeem755/stock-market-data).

# 5.Results
