## Title

Array Pair Sum Divisibility Problem

## Slug

array-pair-sum-divisibility-problem

## Difficulty

Medium

## Description

You are given an array `arr[]` of size `n` and an integer `k`.  
Your task is to determine whether the array can be divided into pairs such that the `sum of every pair is divisible by 'k'`.

If it is possible, return `"YES"`.  
Otherwise, return `"NO"`.



### Example 1

#### Input
4  
9 7 5 3  
6

#### Output
YES

#### Explanation
The array can be divided into pairs `(9, 3)` and `(7, 5)` where both pairs have sums divisible by `6`.



### Example 2

#### Input
4  
92 75 65 48  
10

#### Output
YES


## Input Format

- The first line contains an integer `n` — the number of elements in the array.  
- The second line contains `n` space-separated integers representing the array elements.  
- The third line contains the integer `k`.



## Output Format

- Return `"YES"` if array elements can be paired such that sum of every pair is divisible by `k`.  
- Otherwise, Return `"NO"`.



## Constraints

- 1 ≤ n ≤ 10⁵  
- 1 ≤ arr[i] ≤ 10⁹  
- 1 ≤ k ≤ 10⁹  
- `n` is even



## Time Limit

1 second

## Memory Limit

512 MB



## Tags

arrays, sorting.
