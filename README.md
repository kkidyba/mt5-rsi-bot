# Dynamic RSI Algorithmic Trading Bot (MetaTrader 5)

This repository contains the source code and documentation for a fully automated algorithmic trading strategy developed for MetaTrader 5 using MQL5. This project was created and defended as a Bachelor's Thesis at the Poznań University of Economics and Business.

## Project Overview
The core objective of this bot is to exploit short-term market inefficiencies on the EUR/USD pair using a highly adaptive approach to the Relative Strength Index (RSI). Unlike standard strategies that use static overbought/oversold thresholds (e.g., 70/30), this algorithm calculates **dynamic historical extremes** to trigger market entry.

## Core Technical Features
* **Dynamic Extreme Calculation:** The bot maintains an array of the latest RSI minimums and maximums to calculate a moving average of extremes, adapting to current market volatility.
* **Advanced Risk Management:** * **Global Stop Loss:** Dynamically updated across a grid of averaged positions.
  * **Break Even (BE) & Trailing Stop (TS):** Automated capital protection mechanisms that secure profits once a defined threshold is reached, featuring a reducing distance parameter (`TS_Reducing`).
* **Dynamic Volume Sizing:** The lot size for the initial position is recursively calculated based on the account balance, maximum allowed risk (`RISK_Percent`), and simulated margin requirements for potential future averaged positions.

## Backtest Results (2015-2024)
Extensive backtesting was performed over a 10-year period (M1 timeframe, 'Every tick' modeling).

**Key Finding:** With optimal parameters, the strategy significantly outperformed the S&P 500 index, demonstrating exceptional resilience during bear markets.
* In **2018** (S&P 500: -6.24%), the bot achieved a **+26.67%** return.
* In **2022** (S&P 500: -19.44%), the bot achieved a **+21.31%** return.

Furthermore, statistical analysis of 3,072 parameter configurations revealed that the **Expected Payoff** metric was the most reliable predictor of future strategy performance.

## Repository Structure
* `/src/MultiEntryRSI.mq5` - The main Expert Advisor (EA) source code.
* `/docs/` - Contains the full, academic research paper (Bachelor's Thesis, Polish).

## Author
Wojciech Kidyba
