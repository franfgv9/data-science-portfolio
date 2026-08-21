# Time Series Forecasting: Chilean Consumer Price Index Analysis

## Project Overview
This project provides a comprehensive time series analysis and forecasting study of Chile's Consumer Price Index (CPI), covering the period from 1990 to 2022. The analysis addresses non-stationarity, seasonality, and the recent inflationary shocks observed in the post-pandemic context, comparing standard trend extrapolation with advanced econometric models.

## Main Objectives
* **Characterization:** Decomposition of the CPI series into trend, seasonal, and irregular components.
* **Stationarity Analysis:** Verification of stationarity using the Augmented Dickey-Fuller (ADF) test, requiring regular ($d=1$) and seasonal ($D=1, S=12$) differencing.
* **Model Fitting & Forecasting:** Implementation and comparison of three approaches: Polynomial Baseline, SARIMA(3,1,2)(1,1,1)12, and Triple Exponential Smoothing (TES-m).
* **Performance Evaluation:** Contrast of "fixed multi-step" forecasting versus a realistic "rolling one-step-ahead" evaluation strategy.
* **Multivariate Exploration:** Analysis of contemporaneous correlations and Cross-Correlation Sequences (CCS) between Chile, Mexico, Colombia, and Brazil.

## Technologies
* **Language:** Python
* **Modeling:** statsmodels (ARIMA/SARIMA), Exponential Smoothing, Scikit-learn
* **Visualization:** Matplotlib, Scipy (DFT/FFT analysis)

## Key Findings
* **Model Performance:** While TES (Multiplicative) outperformed SARIMA in direct 24-month multi-step forecasting, **Rolling one-step-ahead SARIMA** proved superior for realistic, updated forecasting, achieving an RMSE of 0.537 and MAPE of 0.366%.
* **Inflationary Adaptation:** Models trained on historical data systematically underestimated the acceleration in inflation observed in 2021-2022. The rolling strategy mitigated this by allowing the model to adapt to changing dynamics month-by-month.
* **Cross-Country Analysis:** Chile shows positive correlations with regional peers, with the strongest temporal associations found with Colombia and Brazil, though these reflect temporal co-movement rather than causality.