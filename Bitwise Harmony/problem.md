## Title  
Bitwise Harmony  

## Slug  
bitwise-harmony  

## Difficulty  
Medium  

## Description  

You are given an integer array `nums` of length `n`.  

In one operation, you may choose any contiguous subarray `nums[l...r]`  
(0 ≤ l ≤ r < n) and replace every element in that subarray  
with the bitwise AND of all its elements.  

Your task is to find the minimum number of operations  
required to make all elements of `nums` equal.  

A subarray is a continuous non-empty sequence of elements within the array.  

## Examples  

### 1  

#### Input  
2  
1 2  

#### Output  
1  

#### Explanation  
Choose `nums[0...1]`: `(1 AND 2) = 0`  
Now the array becomes `[0, 0]`, so all elements are equal in one operation.  

### 2  

#### Input  
3  
5 5 5  

#### Output  
0  

#### Explanation  
All elements are already equal,  
so no operations are needed.  

### 3  

#### Input  
4  
8 4 2 1  

#### Output  
1   

## Input Format  

- First line contains an integer `n` — the size of the array.  
- Second line contains `n` space-separated integers representing the elements of the array.  

## Output Format  

Return a single integer — the minimum number of operations required  
to make all elements of the array equal.  

## Constraints  

1 ≤ n ≤ 10000  
1 ≤ nums[i] ≤ 10⁵  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

bitwise,arrays,greedy,simulation
