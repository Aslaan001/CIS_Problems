## Title
Maximum Sum Trionic Subarray

## Slug
maximum-sum-trionic-subarray

## Difficulty
Hard

## Description

You are given an integer array nums of length n.

A trionic subarray is a contiguous subarray nums[l...r] with 0 ≤ l < r < n, for which there exist indices l < p < q < r such that

1. nums[l...p] is strictly increasing  
2. nums[p...q] is strictly decreasing  
3. nums[q...r] is strictly increasing

Your task is to find the maximum possible sum of any trionic subarray in nums.

It is guaranteed that at least one valid trionic subarray exists.

## Examples

### 1

#### Input
7  
0 -2 -1 -3 0 2 -1

#### Output
-4

### 2

#### Input
4  
1 4 2 7

#### Output
14

## Input Format

The first line contains an integer n.  
The second line contains n integers representing nums.

## Output Format

Return a single integer — the maximum sum of any trionic subarray in nums.

## Constraints

4 ≤ n ≤ 100000  
-10^9 ≤ nums[i] ≤ 10^9

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
two-pointers, dynamic-programming, sliding-window, array

## Company
hackwithinfy
