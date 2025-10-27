## Title

Minimum Shifts to Sort an Array

## Slug

minimum-shifts-to-sort-an-array

## Difficulty

Medium

## Description

You are given an array `arr[]` of `n` integers.  
Using the `Insertion Sort` algorithm, you must determine how many `shifts (element movements)` are required to sort the array in ascending order.

A `shift` occurs when an element is moved one position to the right to make space for inserting the current element in its correct position.

Your task is to `count the total number of shifts performed` while sorting the array using insertion sort.


## Examples

### 1

#### Input


5
2 1 3 1 2

#### Output
4

#### Explanation
Insertion Sort Steps:
[2,1,3,1,2]
→ [1,2,3,1,2] (1 shift)
→ [1,2,3,1,2] (0 shift)
→ [1,1,2,3,2] (2 shifts)
→ [1,1,2,2,3] (1 shift)
Total = 4 shifts

### 2

#### Input
4
1 2 3 4

#### Output
0

#### Explanation
Array already sorted → No shifts needed.

## Input Format
 
- First line: integer `n` — size of the array.  
- Second line: `n` integers representing the array `nums[i]`.

## Output Format

-Single integer — total number of shifts during insertion sort



## Constraints

- 1 ≤ n ≤ 10⁶  
- 1 ≤ nums[i] ≤ 10⁶   


## Time Limit

1 second

## Memory Limit

512 MB



## Tags

arrays, swaps , insertionSort.