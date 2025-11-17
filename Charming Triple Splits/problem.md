## Title  
Charming Triple Splits  

## Slug  
charming-triple-splits  

## Difficulty  
Medium  

## Description  

You are given an integer array nums of length n.  

A split of the array is called charming if it divides nums into three continuous non-empty parts:  
nums1, nums2, and nums3, such that nums = nums1 + nums2 + nums3  
(where + means concatenation).  

The split is valid if one of the following conditions holds:  

1. Prefix Match 1:  
   nums1 is a prefix of nums2.  

2. Prefix Match 2:  
   nums2 is a prefix of nums3.  

Your task is to determine the number of different charming splits that can be made in the array.  

Two splits are considered different if the partition indices differ.  

## Examples  

### 1  

#### Input  
4  
1 1 2 1  

#### Output  
2  

#### Explanation  
The valid charming splits are:  
nums1 = [1], nums2 = [1, 2], nums3 = [1]  
nums1 = [1], nums2 = [1], nums3 = [2, 1]  

### 2  

#### Input  
4  
1 2 3 4  

#### Output  
0  

#### Explanation  
There are no valid splits since no prefix relationship exists between parts.  

### 3  

#### Input  
5  
2 2 2 2 2  

#### Output  
6  

#### Explanation  
Every possible partition forms valid prefixes because all values are identical.  

## Input Format  

First line contains an integer n — the number of elements in the array.  
Second line contains n space-separated integers representing nums.  

## Output Format  

Return a single integer — the total number of charming splits that can be made.  

## Constraints  

1 ≤ n ≤ 5000  
0 ≤ nums[i] ≤ 50  

## Time Limit  
1 second  

## Memory Limit  
512 MB  

## Tags  
array
