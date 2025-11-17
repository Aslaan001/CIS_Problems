## Title  
Maximum Loot Without Alerting Security

## Slug  
maximum-loot-without-alerting-security

## Difficulty  
Medium

## Description  

You are given an array `vals` where each element represents the amount of money stored in a house along a street.  
However, the security system will be triggered if two `adjacent` houses are looted on the same night.

Your task is to determine the `maximum total money` that can be collected without robbing two neighboring houses.

You may choose any number of houses to loot, as long as no two chosen houses are next to each other.

Return the maximum possible sum.

  
## Examples  

### 1  

#### Input  
4  
1 2 3 1  

#### Output  
4  

#### Explanation  
The best choice is: loot house with value `1` and house with value `3`.  
Total = 1 + 3 = 4.


### 2  

#### Input  
5  
2 7 9 3 1  

#### Output  
12  

#### Explanation  
The best choice is:  
2 + 9 + 1 = 12.


## Input Format  

- The first line contains an integer `n` — the number of houses.  
- The second line contains `n` space-separated integers `vals[i]`, where `vals[i]` is the amount of money in the `i`-th house.  


## Output Format  

Return a single integer — the maximum total amount that can be looted.


## Constraints  

- 1 ≤ n ≤ 100  
- 0 ≤ vals[i] ≤ 400  


## Time Limit  
1 second  

## Memory Limit  
256 MB  


## Tags  

array, dynamic-programming, greedy
