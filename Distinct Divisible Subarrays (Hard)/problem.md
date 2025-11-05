## Title  
Distinct Divisible Subarrays  

## Slug  
distinct-divisible-subarrays  

## Difficulty  
Hard  

## Description  

You are given an integer array nums sorted in non-decreasing order and a positive integer k.  

A subarray of nums is said to be `divisible` if the sum of its elements is divisible by k.  

Your task is to determine how many `distinct divisible subarrays` exist in nums.  
Two subarrays are considered distinct if their sequences of values differ.  
 


## Examples  

### 1  

#### Input  
3  
1 2 3  
3  

#### Output  
3  

#### Explanation  
The distinct divisible subarrays are:  
[1, 2], [3], and [1, 2, 3].  
Each of these has a sum that is a multiple of 3.  


### 2  

#### Input  
6  
2 2 2 2 2 2  
6  

#### Output  
2  

#### Explanation  
The divisible subarrays are [2, 2, 2] and [2, 2, 2, 2, 2, 2].  
For example, [2, 2, 2] has a sum of 6, which is divisible by 6.  
Subarrays with identical sequences are counted only once.  

## Input Format  

- The first line contains an integer n — the number of elements in the array.  
- The second line contains n space-separated integers representing the array elements.  
- The third line contains an integer k — the divisor value.  


## Output Format  

Return a single integer — the number of distinct divisible subarrays in nums.  


## Constraints  

1 ≤ n ≤ 100000  
1 ≤ nums[i] ≤ 10^9  
nums is sorted in non-decreasing order.  
1 ≤ k ≤ 10^9  


## Time Limit  

1 second  

## Memory Limit  

512 MB  


## Tags  

arrays, prefix-sum.
