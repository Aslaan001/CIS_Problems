## Title

Sort and Find Median

## Slug

sort-and-find-median

## Difficulty

Easy

## Description

You are given an array `arr[]` of `n` integers.  
Your task is to `sort the array in ascending order` and then `find the median` of the sorted array.

If `n` is odd, the median is the middle element of the sorted array.  
If `n` is even, the median is the `average of the two middle elements` (use integer division for even case).


### Example 1

#### Input


5
2 5 1 7 3

#### Output
3.0

#### Explanation
Sorted array = [1, 2, 3, 5, 7]  
Middle element = 3 → `Median = 3`

### 2

#### Input
6
1 2 3 4 5 6

#### Output
3

#### Explanation
Sorted array = [1, 2, 3, 4, 5, 6]  
Two middle elements = 3, 4 → (3 + 4) / 2 = 3 (integer division)

## Input Format
 
- First line contains an integer `n` — the number of elements in the array.  
- Second line contains `n` space-separated integers representing the array.

## Output Format

- Return a single integer — the `median` of the sorted array.




## Constraints

- 1 ≤ n ≤ 10⁶  
- 1 ≤ arr[i] ≤ 10⁶   


## Time Limit

1 second

## Memory Limit

512 MB



## Tags

arrays, sorting.