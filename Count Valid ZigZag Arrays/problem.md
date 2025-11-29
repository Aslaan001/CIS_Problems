## Title
Count Valid ZigZag Arrays

## Slug
count-valid-zigzag-arrays

## Difficulty
Hard

## Description

You are given three integers n, l, and r.

A ZigZag array of length n is an array a[0...n−1] that satisfies:

1. Each element lies in the range [l, r].  
2. No two adjacent elements are equal.  
3. No three consecutive elements form a strictly increasing or strictly decreasing sequence.

Your task is to compute the total number of valid ZigZag arrays of length n.

Since the number of valid arrays may be large, return the answer modulo 1000000007.

## Examples

### 1

#### Input
3 4 5

#### Output
2

### 2

#### Input
3 1 3

#### Output
10

## Input Format

The first line contains three integers n, l, r.

## Output Format

Return a single integer — the total number of valid ZigZag arrays modulo 1000000007.

## Constraints

3 ≤ n ≤ 2000  
1 ≤ l < r ≤ 2000  

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
dynamic programming, prefix sums

## Company
hackwithinfy
