## Title  
Guarded Subarrays  

## Slug  
guarded-subarrays  

## Difficulty  
Hard

## Description  

You are given an integer array `nums` containing distinct elements.  

A `guarded subarray` is a continuous subarray `nums[l...r]`  
that satisfies the following conditions:  

1. The subarray has length at least 3 (r - l + 1 ≥ 3).  
2. The smaller of its two ends is strictly greater than  
   every element inside the subarray.  
   That is,  
   `min(nums[l], nums[r]) > max(nums[l+1 ... r-1])`.  

Your task is to count the total number of such guarded subarrays in `nums`.  

## Examples  

### 1  

#### Input  
5  
2 5 3 1 4  

#### Output  
2  

#### Explanation  
Valid guarded subarrays are `[3, 1, 4]` and `[5, 3, 1, 4]`.  
For `[3, 1, 4]`: min(3, 4) = 3 > max(1) = 1  
For `[5, 3, 1, 4]`: min(5, 4) = 4 > max(3, 1) = 3  

### 2  

#### Input  
5  
5 1 2 3 4  

#### Output  
3  

#### Explanation  
Valid guarded subarrays are `[5, 1, 2]`, `[5, 1, 2, 3]`, and `[5, 1, 2, 3, 4]`.  

### 3  

#### Input  
3  
1000000000 999999999 999999998  

#### Output  
0  

#### Explanation  
No subarray satisfies the guarded condition.  

## Input Format  

- First line contains an integer `n` — the number of elements in the array.  
- Second line contains `n` space-separated integers representing `nums`.  

## Output Format  

Return a single integer — the total number of guarded subarrays in the array.  

## Constraints  

3 ≤ n ≤ 10⁵  
1 ≤ nums[i] ≤ 10⁹  
All elements of `nums` are distinct.  

## Time Limit  
1 second  

## Memory Limit  
512 MB  

## Tags  
array, two-pointers, stack, sliding-window  
