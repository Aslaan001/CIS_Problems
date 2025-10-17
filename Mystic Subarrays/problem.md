## Title

Mystic Subarrays


## Slug

mystic-subarrays



## Difficulty

Medium

## Description

You have discovered a mystical sequence of numbers said to hold a secret balance between addition and multiplication.  
Each number in the sequence represents a magical value.  

Your task is to count the number of `subarrays` where the `sum of elements equals the product of elements`.  

A subarray is defined as a contiguous sequence of elements within the array.

Return the `total count` of such subarrays.



 


## Examples

### 1

#### Input

4
1 2 3 2

#### Output
5

#### Explanation

All subarrays where sum = product are:  
- `[1]` → sum = 1, product = 1  
- `[2]` (first one) → sum = 2, product = 2  
- `[3]` → sum = 3, product = 3  
- `[2]` (last one) → sum = 2, product = 2  
- `[1, 2, 3]` → sum = 6, product = 6  
    


### 2

#### Input

3
2 2 2    

#### Output

3

#### Explanation

All valid subarrays: `[2]`, `[2]`, `[2]`, `[2,2]`, `[2,2]`  
No other subarray satisfies sum = product. Total = 5.


## Input Format  


- First line: integer `n` — the number of elements in the array.  
- Second line: `n` space-separated integers `arr[i]`.


## Output Format  

- A single integer — the count of subarrays where the sum equals the product.
  

## Constraints  

- 1 ≤ n ≤ 10³  
- 1 ≤ arr[i] ≤ 10⁴      

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
