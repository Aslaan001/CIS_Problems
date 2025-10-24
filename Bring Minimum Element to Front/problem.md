## Title

Bring Minimum Element to Front


## Slug

bring-minimum-element-to-front


## Difficulty

Easy

## Description


You are given an array of integers.  

Your task is to find the `smallest element` in the array and `swap it with the first element`.  

After the swap return the updated array.  

If the smallest element is already at the first position, the array remains unchanged.
 


## Examples

### 1

#### Input

5
5 3 4 2 1 

#### Output
1 3 4 2 5

#### Explanation
The minimum element is `1`.  
After swapping it with the first element (`5`), the array becomes `[1, 3, 4, 2, 5]`.


### 2

#### Input

4
2 1 3 4 

#### Output

1 2 3 4

#### Explanation

The smallest element `1` is at index 2 (0-based), so it is swapped with the first element (`2`).


## Input Format  

- First line: integer `n` — number of elements in the array.  
- Second line: `n` space-separated integers `arr[i]` — elements of the array.

## Output Format  

- Return the array after performing the required swap.
  

## Constraints  

- 1 ≤ n ≤ 10⁴  
- -10⁹ ≤ arr[i] ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays, swapping . 
