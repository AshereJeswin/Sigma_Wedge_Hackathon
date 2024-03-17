# Sigma Internship Coding Challenge

## Overview
This repository presents my solution to the Sigma Wedge Hackathon. The challenge is centered around algorithmic trading with the objective of maximizing portfolio value through strategic buy orders. Focusing specifically on Apple Inc. (AAPL) stock for the year 2023, the model employs a trading strategy that classifies market states, calculates a Transition Probabilities Matrix, and determines the optimal moments to execute buy orders based on daily stock price movements.

## OUTPUT
#### The Output of each approach is explained below :
Each approach aligns with dynamic programming and value iteration principles, focusing on optimizing portfolio value through informed decisions based on state transitions and their probabilities, without forecasting future prices. Here's a condensed overview of the approach:

##### Dynamic Programming and Value Iteration: 
The class enhances portfolio value over time by making sequential decisions that are grounded in current and historical data. This approach is rooted in dynamic programming and value iteration, aiming to derive an optimal policy that maximizes expected returns.

##### State Transitions and Probabilities:
##### State Classification:
It categorizes each day into 'bull', 'flat', or 'bear' states according to daily returns, essential for tracking market state transitions.
##### Transition Probabilities: 
The class maintains a transition probability matrix, updated in a streaming fashion with each new piece of data. This process dynamically calculates the likelihood of moving between states ('bull', 'flat', 'bear'), based on observed historical transitions, thus avoiding any predictive modeling.
##### Decision Making Based on Probabilities: 
Buy decisions are predicated on the current state's transition probabilities. If the probability of moving to a 'bull' state from the current state exceeds that of moving to a 'bear' state, a buy decision is made for the subsequent day.

##### Executing Trades and Portfolio Management:
##### Trade Execution: 
The portfolio value is updated according to the buy decision and the actual state transition, following a pre-defined value function.
##### Buy Indices: 
Identifies the days on which buy decisions are made, pinpointing optimal times for executing buy orders.

## Approach - 1 Output
##### Final Portfolio Value: 27
##### Buy Indices: [3, 6, 8, 10, 11, 12, 13, 14, 15, 16, 17, 19, 20, 21, 22, 24, 26, 27, 28, 30, 32, 34, 37, 40, 41, 42, 44, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 58, 59, 60, 61, 62, 63, 65, 67, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 98, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 129, 133, 134, 135, 137, 142, 143, 144, 146, 160, 162, 164, 165, 166, 167, 168, 177, 178, 187, 188, 189, 190, 191, 192, 193, 194, 195, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 238, 239, 240, 241, 242]

## Approach - 2 Output
##### Final portfolio value: V(N) = 14.0
##### Optimal buy indices: [2, 5, 6, 9, 11, 13, 14, 19, 21, 22, 23, 24, 25, 26, 27, 28, 29, 31, 32, 33, 34, 35, 37, 38, 40, 41, 42, 43, 44, 46, 47, 49, 50, 53, 55, 56, 57, 58, 60, 62, 63, 65, 66, 67, 69, 70, 72, 73, 75, 76, 77, 78, 80, 81, 82, 83, 85, 86, 88, 89, 90, 91, 92, 94, 95, 97, 100, 101, 102, 103, 104, 106, 108, 109, 110, 114, 117, 118, 119, 122, 123, 126, 127, 129, 131, 132, 133, 135, 136, 137, 139, 140, 141, 143, 144, 145, 146, 148, 149, 150, 151, 153, 154, 157, 159, 162, 165, 166, 168, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 184, 186, 188, 190, 191, 192, 193, 195, 196, 197, 198, 199]

## Approach - 3 Output
##### Final Portfolio Value: 14
##### Optimal Buy Indices: [2, 9, 11, 19, 29, 35, 38, 44, 50, 53, 58, 60, 63, 67, 70, 73, 83, 92, 110, 114, 127, 137, 141, 157, 159, 162, 166, 168, 182, 184, 188]

## Approach - 4 Output
##### Final Portfolio Value: 13
##### Optimal Buy Indices: [2, 9, 11, 19, 29, 35, 38, 44, 50, 53, 58, 60, 63, 67, 70, 73, 83, 92, 110, 114, 127, 137, 141, 157, 159, 162, 166, 168, 182, 184, 188]

## Approach - 5 Output
##### Final Portfolio Value: 138.0
##### Buy Indices: [0, 1, 4, 5, 6, 8, 10, 12, 13, 15, 17, 18, 20, 21, 22, 23, 24, 25, 26, 27, 28, 30, 31, 32, 33, 34, 36, 37, 39, 40, 41, 42, 43, 45, 46, 48, 49, 52, 54, 55, 56, 57, 59, 61, 62, 64, 65, 66, 68, 69, 71, 72, 74, 75, 76, 77, 79, 80, 81, 82, 84, 85, 87, 88, 89, 90, 91, 93, 94, 96, 99, 100, 101, 102, 103, 105, 107, 108, 109, 113, 116, 117, 118, 121, 122, 125, 126, 128, 130, 131, 132, 134, 135, 136, 138, 139, 140, 142, 143, 144, 145, 147, 148, 149, 150, 152, 153, 156, 158, 161, 164, 165, 167, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 183, 185, 187, 189, 190, 191, 192, 194, 195, 196, 197, 198]

## Approach- 6 Output
##### Final Portfolio Value: 9.0
##### Buy Indices: [  4   5   6  10  12  13  15  20  21  22  23  24  25  26  27  28  30  31 32  33  34  36  37  39  40  41  42  43  45  46  48  49  52  54  55  56 57  59  61  62  64  65  66  68  69  71  72  74  75  76  77  79  80  81 82  84  85  87  88  89  90  91  93  94  96  99 100 101 102 103 105 107 108 109 113 116 117 118 121 122 125 126 128 130 131 132 134 135 136 138 139 140 142 143 144 145 147 148 149 150 152 153 156 158 161 164 165 167 169 170 171 172 173 174 175 176 177 178 179 180 181 183 185 187 189 190 191 192 194 195 196 197 198]

## Approach - 7 Output
##### Final Portfolio Value: 40.0
##### Optimal Buy Indices: [5, 7, 11, 15, 20, 27, 29, 40, 49, 51, 58, 60, 68, 78, 84, 87, 93, 99, 102, 107, 109, 112, 116, 119, 122, 132, 141, 159, 163, 176, 186, 190, 206, 208, 211, 215, 217, 231, 233, 237]

## Getting Started
### Collection of Data
Obtained the closing prices for each trading day within the specified period (January 1, 2023, to December 31, 2023). Closing prices are a critical piece of data for financial analysis and trading strategy development, as they represent the final price at which a stock is traded during a trading session

### Visualizations and Analysis
#### Line Chart
This line chart illustrates the daily closing prices of Apple Inc. (AAPL) stock throughout the year 2023. Each point on the chart represents the stock's closing price on a specific date, plotted along the vertical axis, against time on the horizontal axis. The chart provides a visual representation of the stock's performance over the year, highlighting trends, fluctuations, and potential patterns in the stock's price movement.
![Line Plot](https://github.com/AshereJeswin/Sigma_Wedge_Hackathon/blob/main/Visualizations/Line%20Plot.png)

#### Distribution of Daily Returns
The distribution chart showcases the daily returns of Apple Inc. (AAPL) stock throughout 2023. Daily returns are calculated from the stock's closing prices, reflecting the percentage change from one day to the next. This visualization helps in understanding the volatility and risk associated with AAPL stock over the specified period. By examining the spread and skewness of the returns, we can gain insights into the stock's typical behavior - identifying periods of stability versus those of significant price movements.
![Distributions of daily return](https://github.com/AshereJeswin/Sigma_Wedge_Hackathon/blob/main/Visualizations/distribution%20of%20daily%20returns.JPG)

#### Moving Averages and Close Price
This visualization presents the moving averages alongside the daily closing prices of Apple Inc. (AAPL) stock for the year 2023. Moving averages are calculated for different periods and plotted over the stock's actual closing price to highlight trends and potential points of resistance or support. The daily closing price line provides a direct view of the stock's performance over time, while the moving averages smooth out short-term volatility to reveal underlying trends in the price movement
![Moving Average and closing price](https://github.com/AshereJeswin/Sigma_Wedge_Hackathon/blob/main/Visualizations/Moving%20averages%20and%20closing%20price.png)

#### Bollinger Bands
Bollinger Bands are a type of price envelope developed by John Bollinger in the 1980s. They are volatility bands placed above and below a moving average. Volatility is based on the standard deviation, which changes as volatility increases and decreases. The bands automatically widen when volatility increases and narrow when volatility decreases.
![Bollinger Bands](https://github.com/AshereJeswin/Sigma_Wedge_Hackathon/blob/main/Visualizations/Bollinger%20Bands.png)

## Strategy Development
This section delves into the core aspects of our trading strategy, developed to maximize the portfolio value of Apple Inc. (AAPL) stock throughout 2023 using Quantrocket.

#### Daily Returns Calculation
Our first step involves calculating daily returns for AAPL stock. This is done by comparing the closing price of the stock on any given day (`p(d)`) with its closing price on the previous day (`p(d-1)`), using the formula : r(d) = (p(d) - p(d-1)) / p(d-1)

#### State Classification
Based on the calculated daily returns, we classify the market condition for each day into one of three distinct states:

- **Bull State (+1):** For days when `r(d) >= 0.1`, indicating a significant positive return.
- **Flat State (0):** For days when `-0.1 < r(d) < 0.1`, suggesting minimal market movement.
- **Bear State (-1):** For days when `r(d) <= -0.1`, reflecting a significant negative return.

![AAPL daily returns](https://github.com/AshereJeswin/Sigma_Wedge_Hackathon/blob/main/Visualizations/AAPL%20Daily%20Returns%20State%20Classification.png)

#### Value Function Definition
A value function is then defined to make decisions about placing a buy order for the following day (`d+1`), based on the state transitions observed. The portfolio value (`V(d+1)`) is updated according to the following rules:

- If transitioning to a Bull State from a Flat State (`s(d+1) = 1 & s(d) = 0`), then `V(d+1) = V(d) + 1`.
- If transitioning to a Bear State from a Flat State (`s(d+1) = -1 & s(d) = 0`), then `V(d+1) = V(d) - 1`.
- In all other cases, `V(d+1) = V(d)`.

#### Transition Distribution Calculation
To inform our buying decisions, we calculate the probability distribution for transitioning from the current state (`s(d)`) to other possible states. This involves a detailed analysis of historical data to identify patterns and trends that can predict future market behavior.

## Backtesting
Test our Strategy: Quantrocket provides tools for backtesting your strategies against historical data. I used this feature to test my model's performance, specifically its ability to maximize the portfolio value through strategic buy orders

Before risking any real money, it's crucial to test our strategy against historical data to see how it would have performed in the past. This can be done using backtesting software or backtesting scripts in Python.

Minimalist Approach: Used Python libraries such as pandas for data manipulation and backtrader or QuantConnect for backtesting. These tools allow us to simulate trading decisions based on historical data and evaluate the performance of your strategy
![Backtesting](https://github.com/AshereJeswin/Sigma_Wedge_Hackathon/blob/main/Visualizations/Backtest%20of%20a%20Moving%20Average%20Crossover%20Strategy.JPG)



