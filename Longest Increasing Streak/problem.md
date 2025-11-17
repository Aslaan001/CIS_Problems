## Title  
Longest Increasing Streak  

## Slug  
longest-increasing-streak  

## Difficulty  
Easy  

## Description  

You are given an unsorted array of integers `nums`. Your task is to find the length of the `longest continuous increasing streak` in the array.  

A continuous increasing streak is defined as a subarray `nums[l...r]` where `l < r` and for every `l <= i < r`, `nums[i] < nums[i + 1]`.  

Return the length of the longest streak where the elements are strictly increasing.  

## Examples  

### 1  

#### Input  
5
1 3 5 4 7 

#### Output  
3  

#### Explanation  
The longest continuous increasing streak is `[1, 3, 5]` with length 3.  
Even though `[1, 3, 5, 7]` is an increasing streak, it is not continuous as elements 5 and 7 are separated by 4.  

### 2  

#### Input  
5
2 2 2 2 2

#### Output  
1  

#### Explanation  
The longest continuous increasing streak is `[2]` with length 1. Note that it must be strictly increasing, so all elements must be distinct.  

## Input Format  

- First line contains an integer `n` — the number of elements in the array.  
- Second line contains `n` space-separated integers representing `nums`.  

## Output Format  

Retrun a single integer — the length of the longest continuous increasing streak in the array.  

## Constraints  

1 ≤ n ≤ 10⁴  
-10⁹ ≤ nums[i] ≤ 10⁹  

## Time Limit  
1 second  

## Memory Limit  
512 MB  

## Tags  

array, sliding-window, dynamic-programming
