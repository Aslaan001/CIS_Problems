## Title
Subarray Product Threshold Counter

## Slug
subarray-product-less-than-k

## Difficulty
Medium

## Description
You are given an array `nums` representing readings collected from a sequence of sensors.  
Each reading contributes multiplicatively to a segment’s total activity score.

A contiguous segment of readings is considered *valid* if the `product of all its elements is strictly less than k`.

Your task is to determine `how many such valid contiguous subarrays exist`.

The arrays can be long, so an efficient sliding‑window solution is required.

## Examples

### 1
#### Input
nums = [10, 5, 2, 6], k = 100

#### Output
8

#### Explanation
The 8 contiguous subarrays with product < 100 are:
[10], [5], [2], [6],  
[10, 5], [5, 2], [2, 6], [5, 2, 6]

### 2
#### Input
nums = [1, 2, 3], k = 0

#### Output
0

## Input Format
- First line contains integer `n`
- Second line contains `n` space‑separated integers
- Third line contains integer `k`

## Output Format
- Output a single integer: number of contiguous subarrays whose product is strictly less than `k`.

## Constraints
- 1 ≤ nums.length ≤ 3 × 10⁴  
- 1 ≤ nums[i] ≤ 1000  
- 0 ≤ k ≤ 10⁶

## Time Limit
1 second

## Memory Limit
256 MB

## Tags
array, sliding-window, two-pointer
