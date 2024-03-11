# Sigma Internship Coding Challenge - Quantrocket Trading Strategy

## Overview
This repository contains my solution to the Sigma Internship Coding Challenge, which focuses on developing a trading strategy using the Quantrocket platform. The challenge involves algorithmic trading with the goal of maximizing portfolio value through strategic buy orders based on daily stock data for Apple Inc. (AAPL) for the year 2023.

## Getting Started

### Data Acquisition
- Access and fetch daily closing price data for AAPL stock for the entire year of 2023 from Quantrocket's freely available US stock price data.

## Trading Strategy

### Objective
Develop a simple model to decide on placing buy orders for the next day (d+1) to maximize the portfolio's value.

### Methodology
1. **Price and Returns**: Calculate the daily return \(r(d)\) as \(r(d) = \frac{p(d) - p(d-1)}{p(d-1)}\), where \(p(d)\) is the closing price on day \(d\).
2. **State Classification**: Classify the market state for each day based on the returns:
- Bull State (+1) if \(r(d) \geq 0.1\)
- Flat State (0) if \(r(d) > -0.1\)
- Bear State (-1) if \(r(d) \leq -0.1\)
3. **Value Function**: Decide to place a buy order for day \(d+1\) based on the state transition, updating the portfolio value \(V(d+1)\) accordingly.
4. **Transition Distribution**: Calculate the probability distribution of state transitions in a streaming manner, using historical observations.

### Implementation
- **Code**: Implement the logic in Python, including data fetching, state classification, value calculation, and decision making for buy orders.
- **Execution**: Run the script to evaluate the trading strategy over the given data range and maximize the portfolio value \(V(N)\).

## Results
- Final portfolio value \(V(N)\)
- Indices of days on which optimal buy orders were placed
