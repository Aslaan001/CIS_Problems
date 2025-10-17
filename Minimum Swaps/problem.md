## Title

Minimum Swaps


## Slug

minimum-swaps



## Difficulty

Medium

## Description

You have discovered an ancient array of integers. Each integer holds a magical value, and the sequence is said to unlock a hidden order if arranged properly.

Your task is to find the `minimum number of swaps` required to sort the array in ascending order.  

A swap can exchange any two elements of the array.

Return the `minimum number of swaps` needed to sort the array.



 


## Examples

### 1

#### Input

4
4 3 2 1

#### Output
2

#### Explanation

One possible sequence of swaps:
1. Swap 4 and 1 → `[1, 3, 2, 4]`
2. Swap 3 and 2 → `[1, 2, 3, 4]` 
    


### 2

#### Input

5
2 3 4 1 5   

#### Output

3

#### Explanation

1. Swap 2 and 1 → `[1, 3, 4, 2, 5]`
2. Swap 3 and 2 → `[1, 2, 4, 3, 5]`
3. Swap 4 and 3 → `[1, 2, 3, 4, 5]`  

Total swaps = 3.

## Input Format  

- First line: integer `n` — the number of elements in the array.  
- Second line: `n` space-separated distinct integers `arr[i]`.


## Output Format  

- A single integer — the minimum number of swaps required to sort the array.
  

## Constraints  

- 1 ≤ n ≤ 10000  
- 1 ≤ arr[i] ≤ 10000      

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
