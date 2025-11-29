## Title
Maximize Sum After Bounded Partitions

## Slug
maximize-sum-after-bounded-partitions

## Difficulty
Medium

## Description

You are given an integer array arr and an integer k.

You may divide the array into contiguous segments, where each segment has a length of at most k.  
After dividing, every segment is transformed so that all its elements become equal to the maximum value inside that segment.

Your task is to determine the maximum possible total sum of the array after performing such a partitioning and replacement.

## Examples

### 1

#### Input
7  
1 15 7 9 2 5 10  
3

#### Output
84

#### Explanation
One optimal partitioning transforms the array into:  
15 15 15 9 10 10 10

### 2

#### Input
11  
1 4 1 5 7 3 6 1 9 9 3  
4

#### Output
83

### 3

#### Input
1  
1  
1

#### Output
1

## Input Format

- The first line contains an integer n, the size of the array.  
- The second line contains n space-separated integers.  
- The third line contains the integer k.

## Output Format

Return a single integer — the maximum sum obtainable after partitioning.

## Constraints

1 ≤ n ≤ 500  
0 ≤ arr[i] ≤ 10^9  
1 ≤ k ≤ n

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
array, dynamic-programming

## Company
hackwithinfy
