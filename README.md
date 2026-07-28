# trade-lens-eurusd-forecasting
Time series forecasting of EUR/USD exchange rates using AR, ARIMA, and ARIMAX models.

An academic research project applying time series forecasting models to predict EUR/USD exchange rate movements, comparing four modeling approaches from simple to context-aware.

#Project Overview

Exchange rate volatility creates real risk for businesses, investors, and individuals. This project investigates whether AI/statistical models can extract reliable predictive signal from historical EUR/USD price data — testing the idea that **context matters more than raw historical price alone**.

## Models Compared

| Model | Approach | R² (Test) | Verdict |
|---|---|---|---|
| Linear Regression | Long-term historical relationship | 0.68 | Baseline — solid but insufficient for short-term volatility |
| AR (Autoregressive) | Uses past values of the series | 0.6 | Too simple; loses reliability under high volatility |
| ARIMA | Autoregression + differencing + moving average | 0.8 | Improvement, but blind to sharp downward reversals |
| **ARIMAX** | ARIMA + exogenous variable (Bid Close) | **0.87** | **Best performer** — captures both upward and downward trends |

## Key Finding

Knowing the target variable's own history isn't enough to predict it reliably. Incorporating an external, correlated variable (**Bid Close**) as an exogenous input significantly improved prediction accuracy — from R²=0.68 (Linear Regression) to R²=0.87 (ARIMAX).

## Contents

- [`Trade_Lens_Decoding_EUR_USD_with_AI.pdf.pptx.pdf`](./Trade_Lens_Decoding_EUR_USD_with_AI.pdf.pptx.pdf) — Full project presentation (problem framing, methodology, model-by-model analysis, results)
- [`Analisis_Valor_Moneda_.ipynb`](./Analisis_Valor_Moneda_.ipynb) — Python/Google Colab notebook with data preprocessing, model implementation, and evaluation
- [`Detailed Report.pdf`](./Detailed Report.pdf) — Project Writing Report

## Methods & Data

- **Dataset:** EUR/USD historical price data, 2005–2021
- **Metrics:** RMSE, MAE, R² (train/test split)
- **Tools:** Python (statsmodels, scikit-learn, pandas, matplotlib)

## Next Steps

- Incorporate financial news sentiment analysis as an additional exogenous variable
- Experiment with more complex architectures (e.g., LSTM neural networks)
- Build a user-facing interface for live forecasting

## Authors

Nur Ain Afiqah Shabudin & Kawtharul Jannah Mohd Sukki
