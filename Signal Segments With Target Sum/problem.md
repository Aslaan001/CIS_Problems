## Title

Signal Segments With Target Sum

## Slug

signal-segments-with-target-sum

## Difficulty

Medium

## Description

A monitoring system records a sequence of integer signal values over time.  
Engineers often need to detect segments of this signal where the total intensity matches a specific target value `k`.

You are given an array of integers representing the signal readings.  
Your task is to determine how many `contiguous, non-empty segments (subarrays)` have a total sum exactly equal to `k`.

Return the count of such segments.

## Examples

### 1

#### Input

3  
1 1 1  
2

#### Output  
2

#### Explanation

Two subarrays sum to 2:

- [1, 1] (positions 1–2)  
- [1, 1] (positions 2–3)

### 2

#### Input

3  
1 2 3  
3

#### Output  
2

#### Explanation

Subarrays that sum to 3:

- [1, 2]  
- [3]

## Input Format  

- First line: integer `n` — number of signal readings.  
- Second line: `n` integers `nums[i]`.  
- Third line: integer `k` — target sum.

## Output Format  

-Return a single integer — the number of subarrays whose sum equals `k`.

## Constraints  

- 1 ≤ n ≤ 2 × 10⁴  
- −1000 ≤ nums[i] ≤ 1000  
- −10⁷ ≤ k ≤ 10⁷  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays, prefix-sum, hashing
