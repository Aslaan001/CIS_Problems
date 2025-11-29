## Title
Min-Cost Staircase Jumps

## Slug
min-cost-staircase-jumps

## Difficulty
Medium

## Description

You are climbing a staircase with n + 1 steps, numbered from 0 to n.

You are given a 1-indexed array costs of length n, where costs[i] represents the cost of landing on step i.

From step i, you may jump to step i + 1, step i + 2, or step i + 3.

The cost of jumping from step i to step j is defined as:

costs[j] + (j - i)^2

You begin at step 0 with a total cost of 0.

Your task is to determine the minimum total cost required to reach step n.

## Examples

### 1

#### Input
4  
1 2 3 4

#### Output
13

#### Explanation
One optimal path is 0 → 1 → 2 → 4:

0 → 1 gives cost 1 + 1^2 = 2  
1 → 2 gives cost 2 + 1^2 = 3  
2 → 4 gives cost 4 + 2^2 = 8  

Total cost is 13.

### 2

#### Input
4  
5 1 6 2

#### Output
11

#### Explanation
One optimal path is 0 → 2 → 4:

0 → 2 gives cost 1 + 2^2 = 5  
2 → 4 gives cost 2 + 2^2 = 6  

Total cost is 11.

### 3

#### Input
3  
9 8 3

#### Output
12

#### Explanation
A direct jump is optimal:

0 → 3 gives cost 3 + 3^2 = 12

## Input Format

The first line contains the integer n.  
The second line contains n space-separated integers representing costs[1..n].

## Output Format

Return a single integer, the minimum total cost to reach step n.

## Constraints

1 ≤ n = costs.length ≤ 100000  
1 ≤ costs[i] ≤ 10000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
dynamic-programming, greedy, staircase, optimization

## Company
hackwithinfy
