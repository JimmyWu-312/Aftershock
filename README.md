# Aftershock  
### ARIMA–GARCH Modeling of S&P 500 Volatility (2000–2024)

## Overview

This project analyzes daily S&P 500 closing prices from 2000–2024 using classical financial time series methods.  
The objective is to distinguish between predictable return structure and dynamic volatility evolution.

The study applies:

- ARIMA modeling for conditional mean dynamics  
- ARCH testing for volatility clustering  
- GARCH(1,1) modeling for conditional heteroskedasticity  
- Diagnostic testing for model adequacy and asymmetry  

This project demonstrates how statistical time series models capture key empirical properties of financial markets.

## Research Questions

- Are daily S&P 500 returns predictable?
- Does volatility cluster over time?
- How persistent are volatility shocks?
- Is volatility response symmetric to positive and negative shocks?


## Data

- Daily S&P 500 closing prices  
- Sample period: January 1, 2000 – 2024  
- Log returns computed using first differences of log prices  


## Methodology

### 1. Stationarity Testing
- Augmented Dickey–Fuller (ADF) tests applied to prices and returns
- Prices found to be non-stationary
- Returns confirmed stationary

### 2. Mean Modeling
- ACF and PACF diagnostics
- `auto.arima()` model selection
- ARIMA(1,0,0) with zero mean

### 3. Volatility Modeling
- ARCH LM test confirms conditional heteroskedasticity
- GARCH(1,1) with AR(1) mean equation
- Normal error distribution

### 4. Model Diagnostics
- Ljung–Box tests on residuals
- Ljung–Box tests on squared residuals
- ARCH LM post-estimation
- Sign bias test for volatility asymmetry


## Key Findings

- Prices are non-stationary; returns are stationary.
- Daily returns exhibit minimal economic predictability.
- Strong volatility clustering is present.
- Volatility persistence is high (α + β ≈ 0.985).
- Evidence suggests asymmetric volatility responses.

The results reinforce a core stylized fact of financial markets:

> Returns are largely unpredictable in the mean, but volatility evolves dynamically and persistently over time.


## Tools & Libraries

- R
- tidyverse
- forecast
- tseries
- FinTS
- rugarch
- lubridate
- knitr


## Financial Insight

While return autocorrelation is weak (consistent with weak-form market efficiency), volatility demonstrates strong persistence and clustering, particularly during crisis periods such as 2008–2009 and 2020.

The ARIMA–GARCH framework effectively separates mean unpredictability from time-varying risk dynamics.


## References

- Engle (1982) — ARCH
- Bollerslev (1986) — GARCH
- Campbell, Lo & MacKinlay (1997) — The Econometrics of Financial Markets
- Box, Jenkins, Reinsel & Ljung (2015) — Time Series Analysis
