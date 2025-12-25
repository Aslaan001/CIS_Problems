## Title

Divisible Prefix Subarray Counter

## Slug

divisible-prefix-subarray-counter

## Difficulty

Medium

## Description

A data processing pipeline analyzes sequences of integer values collected over time.  
Each value can be positive, negative, or zero.

For a given sequence `nums` and an integer `k`, the system needs to identify how many `non-empty contiguous subarrays` have a total sum that is divisible by `k`.

A subarray is defined as a continuous segment of the array without rearranging elements.

Your task is to compute the total number of such subarrays whose sum modulo `k` equals zero.

This type of computation is commonly used in analytics pipelines, rolling-sum validation, and modular consistency checks.

## Examples

### 1

#### Input

6  
4 5 0 -2 -3 1  
5

#### Output

7

#### Explanation

The following subarrays have sums divisible by 5:

- [4, 5, 0, -2, -3, 1]  
- [5]  
- [5, 0]  
- [5, 0, -2, -3]  
- [0]  
- [0, -2, -3]  
- [-2, -3]

### 2

#### Input

1  
5  
9

#### Output

0

#### Explanation

No subarray has a sum divisible by 9.

## Input Format

- First line contains an integer n, the number of elements in the array.
- Second line contains n space-separated integers representing the array nums.
- Third line contains an integer k.

## Output Format

- Return a single integer representing the number of subarrays whose sum is divisible by k.

## Constraints

- 1 ≤ n ≤ 30000  
- -10^4 ≤ nums[i] ≤ 10^4  
- 2 ≤ k ≤ 10000  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

array  

## Company

snapchat
