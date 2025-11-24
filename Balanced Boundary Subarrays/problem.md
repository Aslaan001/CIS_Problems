## Title  
Balanced Boundary Subarrays  

## Slug  
balanced-boundary-subarrays  

## Difficulty  
Medium  

## Description  

You are given an integer array nums representing container capacities.  

We define a subarray `nums[l..r]` as `balanced` if it satisfies both conditions:  

1. It has a length of at least 3.  
2. The first and last elements are each equal to the sum of all elements strictly between them.  

Formally,  
`nums[l] = nums[r] = nums[l + 1] + nums[l + 2] + ... + nums[r - 1]`.  

Your goal is to count the total number of `balanced subarrays` in the given array.  



## Examples  

### 1  

#### Input  
5  
9 3 3 3 9  

#### Output  
2  

#### Explanation  
There are two balanced subarrays:  

- 1. `[9, 3, 3, 3, 9]` → 9 = 3 + 3 + 3  
- 2. `[3, 3, 3]` → 3 = 3  

Both satisfy the condition where boundary values equal the interior sum.  


### 2  

#### Input  
5  
1 2 3 4 5  

#### Output  
0  

#### Explanation  
No subarray of length 3 or more meets the balance condition.  


### 3  

#### Input  
6  
-4 4 0 0 -8 -4  

#### Output  
1  

#### Explanation  
The subarray `[-4, 4, 0, 0, -8, -4]` is balanced because both ends are -4, and the middle sum is `4 + 0 + 0 + (-8) = -4`.  


## Input Format  

- The first line contains an integer `n`, the number of elements in the array.  
- The second line contains `n` space-separated integers representing the array nums.  


## Output Format  

Return a single integer — the count of balanced subarrays.  


## Constraints  

3 ≤ n ≤ 100000  
−10^9 ≤ nums[i] ≤ 10^9  


## Time Limit  

1 second  

## Memory Limit  

512 MB  


## Tags  

array, prefix-sum
