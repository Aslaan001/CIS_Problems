## Title  
Prime Portal Path  

## Slug  
prime-portal-path  

## Difficulty  
Hard 

## Description  

You are given an integer array nums of length n.  

You start at index 0, and your goal is to reach index n - 1.  
From any index i, you can move using the following rules:  

1. Adjacent Step:  
   You may jump to index i + 1 or i - 1, if that index is within bounds.  

2. Prime Portal:  
   If nums[i] is a prime number p,  
   you may instantly teleport to any index j ≠ i  
   such that nums[j] % p == 0.  

Your task is to determine the minimum number of jumps required  
to reach the last index (n - 1) from index 0.  

## Examples  

### 1  

#### Input  
4  
1 2 4 6  

#### Output  
2  

#### Explanation  
Start at index 0 → take an adjacent step to index 1.  
At index 1, nums[1] = 2 is prime, so you can teleport to index 3  
because nums[3] = 6 is divisible by 2.  
Total jumps = 2.  

### 2  

#### Input  
5  
2 3 4 7 9  

#### Output  
2  

#### Explanation  
Start at index 0 → adjacent step to index 1.  
At index 1, nums[1] = 3 is prime,  
so you can teleport directly to index 4 since 9 % 3 == 0.  
Total jumps = 2.  

### 3  

#### Input  
4  
4 6 5 8  

#### Output  
3  

#### Explanation  
Since no teleportation is possible,  
you must move step by step: 0 → 1 → 2 → 3.  
Total jumps = 3.  

## Input Format  

First line contains an integer n — the number of elements in the array.  
Second line contains n space-separated integers representing nums.  

## Output Format  

Print a single integer — the minimum number of jumps required  
to reach index n - 1 from index 0.  

## Constraints  

1 ≤ n ≤ 100000  
1 ≤ nums[i] ≤ 1000000  

## Time Limit  
1 second  

## Memory Limit  
512 MB  

## Tags  
graph, breadth-first-search, maths
