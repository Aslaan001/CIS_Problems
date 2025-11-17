## Title  
Split Array Into Monotonic Halves  

## Slug  
split-array-into-monotonic-halves  

## Difficulty  
Medium  

## Description  

You are given an integer array nums.  

You must split it into two non-empty contiguous subarrays:  
- left, which must be strictly increasing  
- right, which must be strictly decreasing  

Your task is to find the minimum possible absolute difference between the sums of left and right.  
If no valid split exists, return -1.  



## Examples  

### 1  

#### Input  
3  
1 3 2  

#### Output  
2  

#### Explanation  
If we split after index 0, left is [1] and right is [3, 2].  
Both conditions are satisfied since [1] is increasing and [3, 2] is decreasing.  
The sums are 1 and 5, and their absolute difference is 4.  

If we split after index 1, left is [1, 3] and right is [2].  
Both parts satisfy the required conditions, and the sums are 4 and 2.  
The absolute difference is 2.  

Among all valid splits, the minimum difference is 2.  


### 2  

#### Input  
4  
1 2 4 3  

#### Output  
4  

#### Explanation  
Splitting after index 1 gives left = [1, 2] and right = [4, 3].  
The left part is strictly increasing and the right part is strictly decreasing.  
Their sums are 3 and 7, and the difference is 4.  

Splitting after index 2 gives left = [1, 2, 4] and right = [3].  
Both are valid, and the difference is also 4.  

The smallest possible difference is 4.  


### 3  

#### Input  
3  
3 1 2  

#### Output  
-1  

#### Explanation  
No valid split exists where the left subarray is strictly increasing and the right subarray is strictly decreasing.  
Therefore, the output is -1.  


## Input Format  

The first line contains an integer n, the number of elements in the array.  
The second line contains n space-separated integers representing nums.  


## Output Format  

Return a single integer, the minimum absolute difference or -1 if no valid split exists.  


## Constraints  

2 ≤ n ≤ 100000  
1 ≤ nums[i] ≤ 100000  


## Time Limit  

1 second  

## Memory Limit  

512 MB  


## Tags  

array
