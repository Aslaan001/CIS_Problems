## Title  
Longest Balanced Progression Subsequence

## Slug  
longest-balanced-progression-subsequence

## Difficulty  
Medium

## Description  

You are given an integer array nums of length n.

A subsequence is called balanced if the difference between every two consecutive elements in the subsequence is the same.  
Your task is to find the length of the longest balanced subsequence that can be formed from nums.

A subsequence is created by removing zero or more elements without changing the order of the remaining elements.

## Examples  

### 1  

#### Input  
4  
3 6 9 12

#### Output  
4

#### Explanation  
The entire array forms a balanced progression with difference 3.

### 2  

#### Input  
5  
9 4 7 2 10

#### Output  
3

#### Explanation  
A longest balanced subsequence is [4, 7, 10].

### 3  

#### Input  
7  
20 1 15 3 10 5 8

#### Output  
4

#### Explanation  
A valid longest balanced subsequence is [20, 15, 10, 5].

## Input Format  

- The first line contains an integer n.  
- The second line contains n integers representing the array nums.

## Output Format  

Return a single integer: the length of the longest balanced progression subsequence.

## Constraints  

2 ≤ n ≤ 1000  
0 ≤ nums[i] ≤ 500  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

dynamic programming.
