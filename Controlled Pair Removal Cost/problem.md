## Title  
Controlled Pair Removal Cost

## Slug  
controlled-pair-removal-cost

## Difficulty  
Medium

## Description  

You are given an array of integers nums of length n.

Your task is to remove all elements from the array while minimizing the total cost.  
The removal follows these rules:

1. If the array has at least 3 elements:  
   Choose any two elements from among the first three positions of the array and remove them.  
   The cost of this removal is equal to the larger value of the two removed elements.

2. If the array has fewer than 3 elements remaining:  
   Remove all remaining elements in one step.  
   The cost for this final removal is the maximum value among the remaining elements.

Your goal is to determine the minimum total cost required to remove all elements from the array.

## Examples  

### 1  

#### Input  
4  
6 2 8 4

#### Output  
12

#### Explanation  
Remove 6 and 8 from the first three elements → cost = 8  
Remaining array: 2 4  
Remove remaining elements → cost = 4  
Total cost = 8 + 4 = 12

### 2  

#### Input  
4  
2 1 3 3

#### Output  
5

#### Explanation  
Remove 2 and 1 → cost = 2  
Remaining array: 3 3  
Remove remaining elements → cost = 3  
Total cost = 2 + 3 = 5

## Input Format  

- The first line contains an integer n, the number of elements in the array.  
- The second line contains n integers representing the array nums.

## Output Format  

Return a single integer representing the minimum total cost needed to remove all elements.

## Constraints  

1 ≤ n ≤ 1000  
1 ≤ nums[i] ≤ 10^6  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

greedy.
