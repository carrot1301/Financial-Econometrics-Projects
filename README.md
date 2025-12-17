# Macro-Economic Risk Quantification & Model Assessment

## 📌 Project Overview
This project applies quantitative methods to assess the sensitivity of financial assets to macroeconomic factors using the **Futures Platform Macro Risk Radar** framework. The analysis focuses on the relationship between **Crude Oil (Macro Factor)** and the **Energy Sector ETF (XLE)**.

## 🛠 Technologies & Tools
* **Language:** Python
* **Libraries:** `yfinance` (Data), `pandas` (Manipulation), `statsmodels` (Econometrics), `seaborn/matplotlib` (Visualization).
* **Platform:** Google Colab.

## 📊 Key Analysis Steps
1.  **Data Acquisition:** Fetched 5-year daily historical data via Yahoo Finance API.
2.  **Transformation:** Converted prices to **Log Returns** to ensure stationarity.
3.  **Descriptive Statistics:** Analyzed distribution moments (Volatility, Skewness, Kurtosis) to assess "Fat Tail" risks.
4.  **Stationarity Testing:** Applied **Augmented Dickey-Fuller (ADF)** test to validate time-series properties ($p < 0.05$).
5.  **Modeling:** Built a **Simple Linear Regression (OLS)** model to quantify beta sensitivity.
6.  **Assumption Checks:** Verified homoscedasticity using Residual Plots.

## 📈 Key Findings
* **Correlation:** Strong positive correlation observed between Oil prices and Energy stocks.
* **Sensitivity:** The OLS model suggests that for every 1% change in Oil returns, the Energy ETF changes by approx **$\beta$%** (insert your number).
* **Model Limits:** While $R^2$ is significant, residual analysis suggests the presence of volatility clustering, typical in financial time series.

## ⚠️ Disclaimer
This project is for educational purposes only and does not constitute financial advice.
