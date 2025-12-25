## Title

Target Sum Subarray Counter

## Slug

target-sum-subarray-counter

## Difficulty

Medium

## Description

A financial analytics system processes a continuous stream of transaction values recorded over time.  
Each transaction is represented as an integer, and the complete sequence is stored in an array `nums`.

For audit and reporting purposes, analysts are interested in identifying `contiguous segments of transactions` whose total value equals a specific target amount `k`.

A segment is considered valid if:

- It is a non-empty contiguous subarray.
- The sum of all elements in the subarray is exactly equal to `k`.

Your task is to compute the `total number of such subarrays` present in the given transaction sequence.

This problem is fundamental in time-series analysis, anomaly detection, and cumulative balance tracking.

## Examples

### 1

#### Input

3  
1 1 1  
2

#### Output

2

#### Explanation

The subarrays with sum equal to 2 are:

- [1, 1] (indices 0 to 1)  
- [1, 1] (indices 1 to 2)

### 2

#### Input

3  
1 2 3  
3

#### Output

2

#### Explanation

The valid subarrays are:

- [1, 2]  
- [3]

## Input Format

- First line contains an integer n, the number of elements in the array.
- Second line contains n space-separated integers representing the array nums.
- Third line contains an integer k, the target sum.

## Output Format

- Return a single integer representing the number of subarrays whose sum equals k.

## Constraints

- 1 ≤ n ≤ 20000  
- -1000 ≤ nums[i] ≤ 1000  
- -10⁷ ≤ k ≤ 10⁷  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

array  


## Company

quora
