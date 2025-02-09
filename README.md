# HTF Z-Score Trading Strategy (PineScript)

This repository contains a PineScript implementation of a Higher Timeframe (HTF) Z-Score trading strategy.  This strategy aims to identify potential trading opportunities by comparing the current price to a higher timeframe's closing price, normalized using a Z-score.

## Strategy Description

The core idea behind this strategy is to leverage the context of a higher timeframe to filter out noise and potentially identify more significant price movements. The strategy calculates a Z-score, which measures how far the current price deviates from a moving average of recent prices, relative to the standard deviation of those prices.  By comparing this Z-score to pre-defined thresholds, the strategy generates buy and sell signals.

**Key Concepts:**

* **Higher Timeframe (HTF):** The strategy uses price data from a higher timeframe (e.g., 10-minute, 15-minute chart) to provide a broader market context. This helps to filter out short-term fluctuations and focus on more significant trends.
* **Z-Score:** The Z-score is a statistical measure that quantifies how many standard deviations a data point is from the mean (average).  In this strategy, it normalizes the difference between the current price and an Exponential Moving Average (EMA) of recent prices.
* **Exponential Moving Average (EMA):** An EMA is a type of moving average that gives more weight to recent prices, making it more responsive to current market conditions.
* **Trade Baselines (Thresholds):** These are pre-defined Z-score values that trigger buy or sell signals.  When the calculated Z-score crosses above the upper threshold (long threshold), a buy signal is generated. When it crosses below the lower threshold (short threshold), a sell signal is generated.

**Points:**
- Retrieves higher-timeframe (HTF) close prices.
- Calculates an exponential moving average (EMA) and standard deviation on lower timeframe close data.
- Computes a z-score to normalize the difference between HTF close and EMA.
- Generates buy/sell signals based on crossovers of the z-score relative to specified thresholds.

# Parameters:
- HTF Timeframe: The higher timeframe for reference data.
- Z-Score Lookback: Number of bars to calculate standard deviation.
- SSMA Period: Period for the EMA calculation.
- Minute-Based Z-Score Storage Interval: Frequency at which the z-score is updated (for potential smoothing).
- Trade Baselines: Thresholds for triggering long and short entries.

# Pros:
- Uses higher timeframe context to reduce noise.
- Normalizes data via z-score for comparability.

# Cons:
- Lookahead settings might cause repainting if not used carefully but with tab or desktop reload per-minute, false signals can be filtered.
- Simplistic smoothing may require further refinement.

Author: Tugume William Mutara (watchdawg2025)
Copyright © 2025. All rights reserved.
