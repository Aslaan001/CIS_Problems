## Title
Longest Alternating Difference Subsequence

## Slug
longest-alternating-difference-subsequence

## Difficulty
Medium

## Description

You are given an array of integers.

A sequence is considered alternating-difference if the differences between consecutive elements strictly alternate between positive and negative.  
A sequence of length 1, or a sequence of length 2 with distinct values, is always alternating.

A subsequence is formed by removing zero or more elements while keeping the remaining elements in their original order.

Your task is to determine the maximum length of any subsequence whose consecutive differences strictly alternate in sign.

## Examples

### 1

#### Input
6  
1 7 4 9 2 5

#### Output
6

#### Explanation
The full sequence already alternates in sign.

### 2

#### Input
10  
1 17 5 10 13 15 10 5 16 8

#### Output
7

#### Explanation
One valid longest subsequence is:  
1, 17, 10, 13, 10, 16, 8

### 3

#### Input
9  
1 2 3 4 5 6 7 8 9

#### Output
2

#### Explanation
Differences never change sign. Any two increasing values form a valid subsequence.

## Input Format

- The first line contains an integer n.  
- The second line contains n space-separated integers.

## Output Format

Return a single integer: the length of the longest alternating-difference subsequence.

## Constraints

1 ≤ n ≤ 1000  
0 ≤ nums[i] ≤ 1000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
array, greedy, dynamic-programming

## Company
hackwithinfy
