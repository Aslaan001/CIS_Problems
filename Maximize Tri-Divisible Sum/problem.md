## Title
Maximize Tri-Divisible Sum

## Slug
maximize-tri-divisible-sum

## Difficulty
Medium

## Description

You are given an array of integers representing resource values.

Your task is to choose any subset of these values such that the total sum of the selected elements is divisible by 3. Among all possible valid subsets, you must return the maximum achievable sum.

If no non-empty subset satisfies the condition, the empty subset (with sum 0) is allowed and is divisible by 3.

Your goal is to compute this maximum tri-divisible sum.

## Examples

### 1

#### Input
5  
3 6 5 1 8

#### Output
18

#### Explanation
A possible optimal subset is [3, 6, 1, 8], which sums to 18.  
This is divisible by 3 and is the maximum possible sum.

### 2

#### Input
1  
4

#### Output
0

#### Explanation
4 alone is not divisible by 3.  
Thus, the empty subset gives sum 0.

### 3

#### Input
5  
1 2 3 4 4

#### Output
12

#### Explanation
Selecting [1, 3, 4, 4] yields a total of 12, which is divisible by 3.

## Input Format

- The first line contains an integer n.  
- The second line contains n space-separated integers.

## Output Format

Return a single integer: the maximum sum divisible by 3.

## Constraints

1 ≤ n ≤ 40000  
1 ≤ nums[i] ≤ 10000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
array, greedy, dynamic-programming, modulo


## Company
hackwithinfy