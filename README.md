# HTF-Z-Score-Trading-Strategy

//@version=6
// HTF Z-Score Trading Strategy
// -----------------------------
// Description:
//     - Retrieves higher-timeframe (HTF) close prices.
//     - Calculates an exponential moving average (EMA) and standard deviation on lower timeframe close data.
//     - Computes a z-score to normalize the difference between HTF close and EMA.
//     - Generates buy/sell signals based on crossovers of the z-score relative to specified thresholds.
    
// Parameters:
//     - HTF Timeframe: The higher timeframe for reference data.
//     - Z-Score Lookback: Number of bars to calculate standard deviation.
//     - SSMA Period: Period for the EMA calculation.
//     - Minute-Based Z-Score Storage Interval: Frequency at which the z-score is updated (for potential smoothing).
//     - Trade Baselines: Thresholds for triggering long and short entries.
    
// Pros:
//     - Uses higher timeframe context to reduce noise.
//     - Normalizes data via z-score for comparability.
    
// Cons:
//     - Lookahead settings might cause repainting if not used carefully but with tab or desktop reload per-minute, false signals can be filtered.
//     - Simplistic smoothing may require further refinement.
    
// Author: Tugume William Mutara (watchdawg2025)
// Copyright © 2025. All rights reserved.
