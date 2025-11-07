## Title  
Minimum Weight Difference Pairing

## Slug  
minimum-weight-difference-pairing

## Difficulty  
Medium

## Description  

You are given an array `weights`, where each element represents the weight of an item.

You repeatedly perform the following operation:

- Select any two items with weights `a` and `b` (assume `a ≤ b`).
- If `a == b`, both items are removed from the collection.
- Otherwise, the lighter item is removed and the heavier item is replaced with the value `b - a`.

After performing zero or more such operations, at most one item will remain.

Your task is to determine the `smallest possible weight` of the remaining item.  
If all items are removed, return `0`.

## Examples  

### 1  

#### Input  
6  
2 7 4 1 8 1

#### Output  
1

### 2  

#### Input  
5  
31 26 33 21 40

#### Output  
5

## Input Format  

- The first line contains an integer `n` — the number of items.  
- The second line contains `n` space-separated integers representing the weights.

## Output Format  

Return a single integer — the minimum achievable remaining weight.

## Constraints  

1 ≤ n ≤ 30  
1 ≤ weights[i] ≤ 100  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

dynamic programming.
