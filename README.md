# Blockhouse
Assignment for Blockhouse

Overview
This project implements a back-test for a static Smart Order Router based on the Cont & Kukanov (2013) cost model. The router splits a 5,000-share buy order across multiple venues using three tunable parameters:

lambda_over: penalty per extra share bought

lambda_under: penalty for unfilled quantity

theta_queue: queue risk penalty

The optimal allocation is computed as per allocator_pseudocode.txt. The script benchmarks the tuned router against:

Best Ask

TWAP (Time-Weighted Average Price)

VWAP (Volume-Weighted Average Price)

Code Structure
backtest.py: Main script that:

Preprocesses data from l1_day.csv

Implements allocator and cost computation as described

Performs grid search over parameters

Executes and compares three baseline strategies

Outputs a structured JSON of results

Parameter Search
A brute-force grid search is used over:

lambda_over: [0.1, 1, 10]

lambda_under: [0.1, 1, 10]

theta_queue: [0.1, 1, 10]

Each parameter triple is tested to minimize total cost over the full back-test window.










