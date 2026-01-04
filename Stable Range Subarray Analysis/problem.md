## Title  
Stable Range Subarray Analysis  

## Slug  
stable-range-subarray-analysis  

## Difficulty  
Medium  

## Description  

A data analytics system processes a sequence of numerical readings collected over time. Each reading represents a measured value recorded at a specific index.

You are given a 0-indexed integer array nums representing these readings.

A subarray is considered stable if, for the chosen contiguous range of indices i to j, the absolute difference between any two elements within that subarray does not exceed 2.

Formally, a subarray nums[i..j] is stable if for every pair of indices i ≤ p, q ≤ j:

0 ≤ |nums[p] - nums[q]| ≤ 2

Your task is to compute the total number of stable subarrays in the given array.

A subarray must be contiguous and non-empty.

## Examples  

### 1  

#### Input  
4  
5 4 2 4  

#### Output  
8  

#### Explanation  

Stable subarrays of size 1:  
[5], [4], [2], [4]  

Stable subarrays of size 2:  
[5, 4], [4, 2], [2, 4]  

Stable subarrays of size 3:  
[4, 2, 4]  

There are no stable subarrays of size 4.  

Total stable subarrays = 4 + 3 + 1 = 8  

### 2  

#### Input  
3  
1 2 3  

#### Output  
6  

#### Explanation  

Stable subarrays of size 1:  
[1], [2], [3]  

Stable subarrays of size 2:  
[1, 2], [2, 3]  

Stable subarrays of size 3:  
[1, 2, 3]  

Total stable subarrays = 3 + 2 + 1 = 6  

## Input Format  

- The first line contains an integer n — the number of elements in the array.  
- The second line contains n space-separated integers representing the array elements.  

## Output Format  

Return a single integer — the total number of stable subarrays.  

## Constraints  

1 ≤ n ≤ 100000  
1 ≤ nums[i] ≤ 10^9  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

array, queue.  
