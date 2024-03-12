# Sigma Internship Coding Challenge

## Overview
This repository presents my solution to the Sigma Wedge Hackathon. The challenge is centered around algorithmic trading with the objective of maximizing portfolio value through strategic buy orders. Focusing specifically on Apple Inc. (AAPL) stock for the year 2023, the model employs a trading strategy that classifies market states, calculates a Transition Probabilities Matrix, and determines the optimal moments to execute buy orders based on daily stock price movements.

## Getting Started

### Collection of Data
Obtained the closing prices for each trading day within the specified period (January 1, 2023, to December 31, 2023). Closing prices are a critical piece of data for financial analysis and trading strategy development, as they represent the final price at which a stock is traded during a trading session

### Visualizations and Analysis
#### Line Chart
This line chart illustrates the daily closing prices of Apple Inc. (AAPL) stock throughout the year 2023. Each point on the chart represents the stock's closing price on a specific date, plotted along the vertical axis, against time on the horizontal axis. The chart provides a visual representation of the stock's performance over the year, highlighting trends, fluctuations, and potential patterns in the stock's price movement.

#### Distribution of Daily Returns
The distribution chart showcases the daily returns of Apple Inc. (AAPL) stock throughout 2023. Daily returns are calculated from the stock's closing prices, reflecting the percentage change from one day to the next. This visualization helps in understanding the volatility and risk associated with AAPL stock over the specified period. By examining the spread and skewness of the returns, we can gain insights into the stock's typical behavior - identifying periods of stability versus those of significant price movements.

#### Moving Averages and Close Price
This visualization presents the moving averages alongside the daily closing prices of Apple Inc. (AAPL) stock for the year 2023. Moving averages are calculated for different periods and plotted over the stock's actual closing price to highlight trends and potential points of resistance or support. The daily closing price line provides a direct view of the stock's performance over time, while the moving averages smooth out short-term volatility to reveal underlying trends in the price movement

#### Bollinger Bands
Bollinger Bands are a type of price envelope developed by John Bollinger in the 1980s. They are volatility bands placed above and below a moving average. Volatility is based on the standard deviation, which changes as volatility increases and decreases. The bands automatically widen when volatility increases and narrow when volatility decreases.

## Strategy Development
This section delves into the core aspects of our trading strategy, developed to maximize the portfolio value of Apple Inc. (AAPL) stock throughout 2023 using Quantrocket.

#### Daily Returns Calculation
Our first step involves calculating daily returns for AAPL stock. This is done by comparing the closing price of the stock on any given day (`p(d)`) with its closing price on the previous day (`p(d-1)`), using the formula : r(d) = (p(d) - p(d-1)) / p(d-1)

#### State Classification
Based on the calculated daily returns, we classify the market condition for each day into one of three distinct states:

- **Bull State (+1):** For days when `r(d) >= 0.1`, indicating a significant positive return.
- **Flat State (0):** For days when `-0.1 < r(d) < 0.1`, suggesting minimal market movement.
- **Bear State (-1):** For days when `r(d) <= -0.1`, reflecting a significant negative return.

#### Value Function Definition
A value function is then defined to make decisions about placing a buy order for the following day (`d+1`), based on the state transitions observed. The portfolio value (`V(d+1)`) is updated according to the following rules:

- If transitioning to a Bull State from a Flat State (`s(d+1) = 1 & s(d) = 0`), then `V(d+1) = V(d) + 1`.
- If transitioning to a Bear State from a Flat State (`s(d+1) = -1 & s(d) = 0`), then `V(d+1) = V(d) - 1`.
- In all other cases, `V(d+1) = V(d)`.

#### Transition Distribution Calculation
To inform our buying decisions, we calculate the probability distribution for transitioning from the current state (`s(d)`) to other possible states. This involves a detailed analysis of historical data to identify patterns and trends that can predict future market behavior.

# OUTPUT
#### Final portfolio value: V(N) = 17

#### Optimal buy indices: [5, 7, 11, 15, 20, 27, 29, 40, 49, 51, 58, 60, 68, 78, 84, 87, 93, 99, 102, 107, 109, 112, 116, 119, 122, 132, 141, 159, 163, 176, 186, 190, 206, 208, 211, 215, 217, 231, 233, 237]

#### Transition Probabilities Matrix:
| From/To | Bear | Flat | Bull |
|---------|------|------|------|
| Bear    | 0.14 | 0.74 | 0.11 |
| Flat    | 0.15 | 0.60 | 0.25 |
| Bull    | 0.12 | 0.68 | 0.20 |

## Backtesting
Test our Strategy: Quantrocket provides tools for backtesting your strategies against historical data. I used this feature to test my model's performance, specifically its ability to maximize the portfolio value through strategic buy orders

Before risking any real money, it's crucial to test our strategy against historical data to see how it would have performed in the past. This can be done using backtesting software or backtesting scripts in Python.

Minimalist Approach: Used Python libraries such as pandas for data manipulation and backtrader or QuantConnect for backtesting. These tools allow us to simulate trading decisions based on historical data and evaluate the performance of your strategy

## Predictive Analysis of Stock Closing Prices Using Polynomial Regression For Next `N` Days
Primarily leveraging polynomial regression to forecast stock closing prices by analyzing the relationship between the day of the year and the stock's closing price. This sophisticated statistical approach enables the prediction of closing prices for a designated number of future trading days, specifically focusing on actual trading days and excluding weekends. 

## Predicted Close Prices for Next 12 Trading Days

|    Date    | Predicted Close Price |
|------------|-----------------------|
| 2024-01-01 |         122.267637    |
| 2024-01-02 |         122.975623    |
| 2024-01-03 |         123.677711    |
| 2024-01-04 |         124.373927    |
| 2024-01-05 |         125.064297    |
| 2024-01-08 |         127.100582    |
| 2024-01-09 |         127.767820    |
| 2024-01-10 |         128.429338    |
| 2024-01-11 |         129.085163    |
| 2024-01-12 |         129.735320    |
| 2024-01-15 |         131.652033    |
| 2024-01-16 |         132.279770    |

#### Calculation Of Portfolio Value, Buy Indices And Transition Probability Matrix
Beyond this predictive analysis, here I calculated the portfolio's projected value based on these forecasts, identified optimal buying opportunities (buying indices) within the forecasted period, and construct a transition probability matrix. This matrix offers insights into the likelihood of shifting between different market states, providing a comprehensive toolkit for informed trading strategies and portfolio optimization

# OUTPUT
#### Final portfolio value: V(N) = 2

#### Optimal buy indices: [5, 10]
#### Transition Probabilities Matrix:
| From/To | Bear | Flat | Bull |
|---------|------|------|------|
| Bear    | 0.00 | 1.00 | 0.00 |
| Flat    | 0.00 | 0.75 | 0.25 |
| Bull    | 0.00 | 1.00 | 0.00 |
