## Title

Minimum Moves to Order

## Slug

minimum-moves-to-order

## Difficulty

Medium

## Description

You are given an array `arr[]` consisting of random ordered integers.  
In one operation, you may swap two `consecutive elements` of the array.  

Your task is to determine the minimum number of adjacent swaps required to sort the array in non-decreasing order.  
Only adjacent swaps are allowed — meaning two elements can only exchange positions if they are next to each other.


## Examples

### 1

#### Input


5
1 5 3 4 2

#### Output
4


#### Explanation
Step 1: Count inversions

(5, 3) → inversion

(5, 4) → inversion

(5, 2) → inversion

(3, 2) → inversion

(4, 2) → inversion

Total inversions = 5 → minimum adjacent swaps = 5



### 2

#### Input

4
1 2 3 4

#### Output

0

#### Explanation

The array is already sorted, so no swaps are needed.


## Input Format  

- First line: integer `n` — number of elements in the array.  
- Second line: `n` space-separated integers `arr[i]`.

## Output Format  

- A single integer — the minimum number of adjacent swaps required to sort the array.
  




## Constraints  

- 1 ≤ n ≤ 10⁵  
- -10⁹  ≤ arr[i] ≤ 10⁹       

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays, swaping . 
