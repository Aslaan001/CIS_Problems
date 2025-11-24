## Title  
Triple Product Maximization After One Change  

## Slug  
triple-product-maximization-after-one-change  

## Difficulty  
Medium  

## Description  

You are given an integer array nums.  

You are allowed to change exactly one element in the array to any integer within the range [-100000, 100000] (inclusive).  

After making this single change, determine the largest possible product of any three distinct elements from the updated array.  

Return the maximum product value that can be achieved.   


## Examples  

### 1 

#### Input  
3  
5 0 9  

#### Output  
4500000  

#### Explanation  
Replacing 0 with -100000 gives the array [5, -100000, 9].  
The product 5 * (-100000) * 9 = -4500000.  
Replacing 0 with 100000 gives [5, 100000, 9], producing 5 * 100000 * 9 = 4500000.  
The maximum possible product is 4500000.  


### 2  

#### Input  
5  
-3 -2 -7 -5 -9  

#### Output  
6300000 

#### Explanation  
-9 * -7 * 1e5 = 6300000


## Input Format  

- The first line contains an integer n, the number of elements in the array.  
- The second line contains n space-separated integers representing the array elements.  


## Output Format  

Return a single integer representing the maximum possible product of any three elements after one allowed replacement.  


## Constraints  

3 ≤ n ≤ 100000  
−100000 ≤ nums[i] ≤ 100000  


## Time Limit  

1 second  

## Memory Limit  

512 MB  


## Tags  

array
