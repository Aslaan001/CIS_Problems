## Title  
Maximum Coins from Bursting Balloons  

## Slug  
maximum-coins-from-bursting-balloons  

## Difficulty  
Hard  

## Description  

You are given `n` balloons, numbered from `0` to `n - 1`.  
Each balloon has a number written on it, represented by the array `vals`.  

When you burst the `i-th` balloon, you earn `vals[i - 1] * vals[i] * vals[i + 1]` coins.  
If `i - 1` or `i + 1` go out of bounds, treat them as balloons with the value `1`.  

Your goal is to burst all the balloons in an order that `maximizes the total number of coins collected`.  

Return the `maximum coins` that can be obtained.  

## Examples  

### 1  

#### Input  
4  
3 1 5 8  

#### Output  
167  

#### Explanation  
Order of bursting:  
- Burst balloon 1 → coins = 3×1×5 = 15, remaining [3,5,8]  
- Burst balloon 0 → coins = 1×3×5 = 15, remaining [5,8]  
- Burst balloon 1 → coins = 1×5×8 = 40, remaining [8]  
- Burst balloon 0 → coins = 1×8×1 = 8  

Total = 15 + 15 + 40 + 8 = 78 (but optimal bursting order gives 167).  

### 2  

#### Input  
2  
1 5  

#### Output  
10  

#### Explanation  
Burst balloon 0 → 1×1×5 = 5  
Burst balloon 1 → 1×5×1 = 5  
Total = 10.  

## Input Format  

- The first line contains an integer `n` — the number of balloons.  
- The second line contains `n` space-separated integers `vals[i]` — the value on each balloon.  

## Output Format  

Return a single integer — the maximum coins you can collect by bursting the balloons optimally.  

## Constraints  

- 1 ≤ n ≤ 300  
- 0 ≤ vals[i] ≤ 100  

## Time Limit  
1 second  

## Memory Limit  
256 MB  

## Tags  
dynamic-programming, divide-and-conquer, interval-dp, optimization  
