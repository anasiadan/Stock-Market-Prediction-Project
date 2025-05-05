# Stock Market Prediction
## 1.Overview
This project aims to predict stock market movements using machine learning techniques on historical stock market data. The system is trained on historical data and can predict future stock prices based on patterns identified in the data. The goal of this project is to predict next-day stock direction (Up/Down) using technical indicators.

## 2.Project Components

### 2.1 Exploratory Data Analysis (EDA)
File: `stock-market-eda.ipynb`

This notebook contains comprehensive data exploration including:
- Data cleaning and preprocessing
- Statistical analysis of historical stock prices
- Visualization of price trends over time
- Correlation analysis between different stock metrics
- Feature distribution analysis
- Time series decomposition to identify seasonal patterns

### 2.2 Prediction Models
File: `stock-market-prediction.ipynb`

This notebook implements various prediction techniques:
- Multiple regression models for price prediction
- Feature engineering to improve prediction accuracy
- Time series forecasting models
- Model evaluation using metrics like RMSE, MAE, and R²
- Visualization of predicted vs actual prices

## 3.Dataset

The data of this project is open source historical stock market data of five major Big Tech companies: NVIDIA (NVDA), Apple (AAPL), Microsoft (MSFT), Google (GOOGL), and Amazon (AMZN) over a 15 years from January 1, 2010 to January 1, 2025. The dataset can be accessed from [Kaggle](https://www.kaggle.com/datasets/marianadeem755/stock-market-data). Features include:
- Date
- Open, High, Low, Close prices
- Adjusted closing prices
- Trading volume

## 4.Technologies Used
- Python 3
- Pandas & NumPy for data manipulation
- Matplotlib & Seaborn for data visualization
- Scikit-learn for machine learning models
- Jupyter Notebooks for interactive development

## 5.How to Use

1. Clone this repository:
```
git clone https://github.com/anasiadan/Stock-Market-Prediction-Project.git
```

2. Install required dependencies:
```
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

3. Open and run the notebooks in order:
   - First `stock-market-eda.ipynb` to understand the data
   - Then `stock-market-prediction.ipynb` to see the prediction models

## 6.Results

### EDA Insights Summary
The exploratory data analysis of the stock market dataset revealed several important patterns. The closing price trends show that most technology stocks, including Apple, Amazon, Microsoft, Google, and NVIDIA, have followed a strong long-term upward trajectory, with notable events like the COVID-19 market dip clearly visible. Correlation analysis indicated that these stocks are highly positively correlated, moving largely in the same direction, which suggests that sector or market-wide dynamics play a major role. Volume analysis revealed that trading activity spikes sharply during periods of market volatility, making volume a potentially powerful feature for predicting unusual market behavior. Moving average plots demonstrated how smoothing techniques can highlight underlying trends and possible trend reversals, offering opportunities for feature engineering using crossover signals. Finally, volatility analysis showed that while most trading days are relatively stable, there are occasional extreme spikes, typically during market shocks, that could be important for modeling risk.

Based on these insights, the following actionable steps are recommended:
- Create lag features using past stock prices and returns to capture momentum and trend patterns.
- Engineer volume-based features, such as volume spikes relative to historical averages, to detect periods of unusual activity.
- Use moving average crossovers (e.g., 50-day vs 200-day) as signals for trend reversals or continuation patterns.
- Incorporate cross-stock relationships by using features from multiple stocks, given their high correlation.
- Model volatility explicitly by creating features that capture large intraday price movements or sudden changes in trading volume.
- Consider sector-wide indicators (like tech sector ETFs) to enhance predictions based on broader market behavior.

### Predictions

Both Random Forest and XGBoost models achieved negative R² scores across all companies, with XGBoost consistently outperforming Random Forest (AAPL: -0.169 vs -0.256, AMZN: -0.178 vs -0.666, MSFT: -0.565 vs -0.696). Trading strategies dramatically underperformed buy-and-hold, with ML strategies producing significant losses in most cases (AMZN: -66% RF, NVDA: -66% XGB). Microsoft was the sole exception with positive ML returns (RF: 27%, XGB: 22%), though these still underperformed buy-and-hold's 54%. NVIDIA's extraordinary 509% buy-and-hold return proved insurmountable for ML models.
Win rates clustered around 46-47%, indicating no better than random directional prediction. Sharpe ratios confirmed poor risk-adjusted performance with all ML strategies showing negative values while buy-and-hold achieved the best ratios.

#### Key takeaways:
- Daily return prediction using technical indicators alone proved insufficient for profitable trading.
- Strong trending markets heavily favor buy-and-hold strategies.
- Current feature set requires enhancement with fundamental data.
- Consider longer prediction horizons for improved performance.
- Results validate market efficiency in short-term price movements


#### Next Steps:
- Implement time series models (LSTM, GRU) to capture sequential dependencies and long-term patterns.
- Integrate fundamental data (earnings, revenue, P/E ratios) and alternative data sources (news sentiment, social media trends).
- Test longer prediction horizons (weekly/monthly) where technical patterns may be more reliable.
- Implement market regime detection to apply strategies only during optimal conditions.
- Develop ensemble models combining multiple prediction timeframes and architectures.
- Test on different market conditions and sectors to validate model robustness.

## License
Open source under the MIT License.