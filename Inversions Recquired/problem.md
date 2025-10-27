## Title

Inversions Recquired

## Slug

inversions-recquired

## Difficulty

Medium

## Description

You are given an integer array `nums` consisting of `n` elements.  
You can swap `only adjacent elements` any number of times.  

Your task is to determine the number of inversions of the array.

This problem essentially measures how far the array is from being sorted — i.e., the number of `inversions` in the array.


## Examples

### 1

#### Input

3
3 2 1

#### Output
3

#### Explanation
Perform the following adjacent swaps:
[3,2,1] → [2,3,1] → [2,1,3] → [1,2,3]
Total swaps = 3.

### 2

#### Input
5
2 1 5 3 4

#### Output
3

#### Explanation
The inversions are (2,1), (5,3), (5,4).  
Hence, minimum swaps = 3.

## Input Format
 
- First line: integer `n` — size of the array.  
- Second line: `n` integers representing the array `nums[i]`.

## Output Format

- A single integer — the minimum number of adjacent swaps required to sort the array.



## Constraints

- 1 ≤ n ≤ 10⁶  
- 1 ≤ nums[i] ≤ 10⁶   


## Time Limit

1 second

## Memory Limit

512 MB



## Tags

arrays, swaps.