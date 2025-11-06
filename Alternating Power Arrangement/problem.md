## Title  
Alternating Power Arrangement  

## Slug  
alternating-power-arrangement  

## Difficulty  
Medium  

## Description  

You are given an integer array nums.  
You can rearrange its elements in any order.  

Define the alternating power score of an array arr as:  

score = arr[0]^2 - arr[1]^2 + arr[2]^2 - arr[3]^2 + ...  

Your task is to find the maximum possible alternating power score that can be obtained by rearranging the elements of nums optimally.  


## Examples  

### 1  

#### Input  
3  
1 2 3  

#### Output  
12  

#### Explanation  
Rearranging nums as [2, 1, 3] gives the maximum alternating score:  
2^2 - 1^2 + 3^2 = 4 - 1 + 9 = 12.  


### 2  

#### Input  
6  
1 -1 2 -2 3 -3  

#### Output  
16  

#### Explanation  
An optimal rearrangement is [-3, -1, -2, 1, 3, 2].  
The alternating score becomes:  
(-3)^2 - (-1)^2 + (-2)^2 - (1)^2 + (3)^2 - (2)^2 = 9 - 1 + 4 - 1 + 9 - 4 = 16.  


## Input Format  

- The first line contains an integer n — the number of elements in the array.  
- The second line contains n space-separated integers representing the elements of nums.  


## Output Format  

Print a single integer — the maximum alternating power score possible after rearranging the elements.  


## Constraints  

1 ≤ n ≤ 100000  
-40000 ≤ nums[i] ≤ 40000  


## Time Limit  

1 second  

## Memory Limit  

512 MB  


## Tags  

arrays, sorting.
