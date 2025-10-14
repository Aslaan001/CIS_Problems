## Title

Maximum Treasure

## Slug

maximum-treasure

## Difficulty

Medium

## Description


Imagine you are exploring a hidden treasure map represented as a sequence of numbers.  
Each number in the array tells you the amount of treasure (positive) or the number of traps (negative) at that spot.  

Your mission is to find the `maximum treasure` you can collect by choosing a single contiguous path along the map.  

Return the total treasure as an integer — the sum of the chosen path.  
 


## Examples

### 1

#### Input

5
3 -2 5 -1 4

#### Output
9

#### Explanation


- Maximum sum subarray = `[3, -2, 5, -1, 4]` → Sum = 9

### 2

#### Input

4
-1 -3 -2 -4

#### Output

-1

#### Explanation

- Maximum sum subarray = `[-1]` → Sum = -1


## Input Format  

- First line: integer `n` — the number of elements in the array.  
- Second line: `n` integers `arr[i]` — the elements of the array.  

## Output Format  

- Return a single integer — maximum sum of any contiguous subarray.  




## Constraints  

- 1 ≤ n ≤ 10000 
- -10⁹ ≤ stars[i] ≤ 10⁹   

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays. 
