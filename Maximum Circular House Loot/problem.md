## Title  
Maximum Circular House Loot

## Slug  
maximum-circular-house-loot

## Difficulty  
Medium

## Description  

You are given an array vals where each element represents the amount of money in a house.  
All houses are arranged in a circle, meaning the first and last houses are also adjacent.

You want to collect the maximum amount of money without looting two neighboring houses,  
otherwise the security alarm will trigger.

Return the maximum total amount that can be collected.


## Examples  

### 1  

#### Input  
3  
2 3 2  

#### Output  
3  


### 2  

#### Input  
4  
1 2 3 1  

#### Output  
4  


### 3  

#### Input  
3  
1 2 3  

#### Output  
3  


## Input Format  

- The first line contains an integer n — the number of houses.  
- The second line contains n space-separated integers vals[i].  


## Output Format  

Return a single integer — the maximum total amount that can be collected.


## Constraints  

- 1 ≤ n ≤ 100  
- 0 ≤ vals[i] ≤ 1000  


## Time Limit  
1 second  

## Memory Limit  
256 MB  


## Tags  
dynamic-programming, circular-array, optimization
