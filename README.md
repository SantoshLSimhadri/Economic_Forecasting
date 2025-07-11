# Comparative Analysis of Forecasting Models for Sony and Take-Two Interactive

## Project Overview
This project explores stock price forecasting using multiple time series models to predict weekly closing prices for Sony and Take-Two Interactive. The analysis compares the effectiveness of ARIMA, SARIMA, and VAR models in capturing stock price movements and evaluates the impact of external variables on forecasting accuracy.

## Objective
- Compare the performance of ARIMA, SARIMA, and VAR models for stock price prediction
- Investigate the role of external variables (trading volume, opening prices, failure events) in forecasting accuracy
- Analyze the differences between univariate and multivariate forecasting approaches

## Data Sources
- **Primary Data**: Bloomberg (Daily stock prices from 1980-2025 for Sony, 1997-2025 for Take-Two)
- **Variables**: Closing price, opening price, trading volume
- **External Data**: Dummy variable for game failures and acquisitions (sourced from Wikipedia)
- **Processing**: Weekly averages calculated to avoid holiday effects

## Methodology

### Models Implemented
1. **ARIMA Models**: Univariate forecasting based on historical stock prices
2. **SARIMA Models**: Seasonal ARIMA to capture seasonal patterns
3. **VAR Models**: Multivariate approach incorporating opening prices, volume, and failure events

### Key Steps
1. **Data Preprocessing**: 
   - Stationarity testing using Augmented Dickey-Fuller (ADF) test
   - First-order differencing applied to achieve stationarity
   - 80/20 train-test split

2. **Model Selection**: 
   - ACF/PACF plot analysis for parameter identification
   - Model evaluation using AIC, BIC, RMSE, and MAE criteria
   - White noise testing for residuals

3. **Forecasting**: Out-of-sample predictions and comparison with real-time values

## Technologies Used
- **R Programming**: Primary analysis environment
- **Libraries**: forecast, tseries, vars
- **Excel**: Data preprocessing and weekly averaging
- **Statistical Tests**: ADF test, residual analysis

## Key Findings

### Sony Stock Results
- **Best ARIMA Model**: ARIMA(2,1,3) - Predicted: $21.76
- **Best SARIMA Model**: ARIMA(2,1,2)(0,1,6)[216] - Predicted: $21.75
- **VAR Model**: Predicted: $21.98 (closest to actual)
- **Actual Price**: $23.62

### Take-Two Stock Results
- **Best ARIMA Model**: ARIMA(9,1,12) - Predicted: $202.22 (most accurate)
- **VAR Model**: Predicted: $206.53
- **Actual Price**: $203.67

## Key Insights
- **Sony**: All models underestimated actual prices; VAR model performed relatively better
- **Take-Two**: ARIMA model provided the most accurate forecast
- **External Variables**: VAR models show promise but require more comprehensive external factors
- **Seasonality**: SARIMA models identified seasonal patterns, particularly in Sony data

## Limitations
- External market sentiment factors not included
- Limited exogenous variables in VAR models
- Dummy variable approach may not capture all relevant events
- Models struggled to predict significant upward price movements

## Model Performance Metrics
Evaluation based on:
- **AIC/BIC**: Model selection criteria
- **RMSE**: Root Mean Squared Error
- **MAE**: Mean Absolute Error
- **White Noise Tests**: Residual analysis

## Future Improvements
- Incorporate additional external variables (market sentiment, economic indicators)
- Explore machine learning approaches (LSTM, Random Forest)
- Enhance dummy variable methodology for external events
- Consider ensemble methods combining multiple models
