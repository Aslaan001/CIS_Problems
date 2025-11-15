## Title  
Maximum Profit from Multiple Stock Trades  

## Slug  
maximum-profit-multiple-trades  

## Difficulty  
Medium  

## Description  

You are given an integer array `prices`, where `prices[i]` represents the price of a stock on the `i-th` day.  

You may perform as many buy-sell transactions as you like, with the only restriction that you can hold at most one stock at a time.  
You may buy and sell on the same day, but you cannot hold more than one stock simultaneously.  

Your task is to determine the maximum total profit that can be achieved.  

If no profitable trades are possible, return `0`.  

## Examples  

### 1  

#### Input  
6  
7 1 5 3 6 4  

#### Output  
7  

#### Explanation  
Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 4.  
Buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 3.  
Total profit = 4 + 3 = 7.  

### 2  

#### Input  
5  
1 2 3 4 5  

#### Output  
4  

#### Explanation  
Buy on day 1 and sell on day 5 for a total profit of 4.  

### 3  

#### Input  
5  
7 6 4 3 1  

#### Output  
0  

#### Explanation  
There are no increasing pairs of prices, so no profitable transaction is possible.  

## Input Format  

- The first line contains an integer `n` — the number of days.  
- The second line contains `n` space-separated integers representing the daily stock prices.  

## Output Format  

Return a single integer — the maximum possible profit achievable through any number of transactions.  

## Constraints  

- 1 ≤ n ≤ 30000  
- 0 ≤ prices[i] ≤ 10000  

## Time Limit  
1 second  

## Memory Limit  
256 MB  

## Tags  
greedy, dynamic-programming, arrays, stock-trading  
