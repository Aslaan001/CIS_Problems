## Title  
Maximum Length Sequence Summing to Target

## Slug  
maximum-length-sequence-summing-to-target

## Difficulty  
Medium

## Description  

You are given an integer `target` and an array `nums` of positive integers.

Your task is to find the `maximum number of elements` you can select from `nums` such that:
- The selected elements appear in the `same order` as in the original array.
- Their total sum is `exactly equal` to `target`.

If no valid selection exists, return `-1`.



## Examples  

### 1  

#### Input  
5  
1 2 3 4 5  
9  

#### Output  
3  

#### Explanation  
Possible selections summing to 9 include:  
- 1 + 3 + 5  
- 2 + 3 + 4  
The longest valid length is `3`.  


### 2  

#### Input  
6  
4 1 3 2 1 5  
7  

#### Output  
4  

#### Explanation  
A longest valid selection is:  
1 + 3 + 2 + 1 = 7  
Length = 4.  


### 3  

#### Input  
5  
1 1 5 4 5  
3  

#### Output  
-1  


## Input Format  

- The first line contains an integer `n` — the size of the array.  
- The second line contains `n` space-separated integers `nums[i]`.  
- The third line contains the integer `target`.  


## Output Format  

Return a single integer — the maximum length of any subsequence that sums to `target`, or `-1` if no such subsequence exists.  


## Constraints  

- 1 ≤ n ≤ 1000  
- 1 ≤ nums[i] ≤ 1000  
- 1 ≤ target ≤ 1000  


## Time Limit  

1 second  

## Memory Limit  

256 MB  


## Tags  

array, dynamic-programming
