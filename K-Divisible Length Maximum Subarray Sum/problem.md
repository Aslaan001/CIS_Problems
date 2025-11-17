## Title  
K-Divisible Length Maximum Subarray Sum  

## Slug  
k-divisible-length-maximum-subarray-sum  

## Difficulty  
Medium  

## Description  

You are given an integer array nums and a positive integer k.  

A subarray of nums is said to be `valid` if the length of the subarray is divisible by k.  

Your task is to determine the `maximum possible sum` of such a valid subarray.  
If all subarrays with length divisible by k have negative sums, return the largest (least negative) among them.  

## Examples  

### 1  

#### Input  
2  
1 2  
1  

#### Output  
3  

#### Explanation  
The subarray [1, 2] has a sum of 3 and its length 2 is divisible by 1.  

### 2  

#### Input  
5  
-1 -2 -3 -4 -5  
4  

#### Output  
-10  

#### Explanation  
The valid subarray [-1, -2, -3, -4] has a sum of -10 and its length 4 is divisible by 4.  

### 3  

#### Input  
5  
-5 1 2 -3 4  
2  

#### Output  
4  

#### Explanation  
The valid subarray [1, 2, -3, 4] has a sum of 4 and its length 4 is divisible by 2.  

## Input Format  

- The first line contains an integer n — the number of elements in the array.  
- The second line contains n space-separated integers representing the array elements.  
- The third line contains an integer k — the divisor value for subarray length.  

## Output Format  

Return a single integer — the maximum sum of a subarray whose length is divisible by k.  

## Constraints  

1 ≤ k ≤ n ≤ 200000  
-10^9 ≤ nums[i] ≤ 10^9  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

array, dynamic-programming, prefix-sum 
