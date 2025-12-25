## Title

Array Reconstruction Using Cumulative Replacement

## Slug

array-reconstruction-using-cumulative-replacement

## Difficulty

Hard

## Description

A data transformation engine starts with an array `arr` of length `n`, where every element is initialized to `1`.

The system allows the following operation to be performed repeatedly:

- Let `x` be the sum of all elements currently present in the array.
- Choose any index `i` such that `0 ≤ i < n`.
- Replace the value at index `i` with `x`.

Using this operation any number of times, the system attempts to transform the initial array into a given target array `target`.

Your task is to determine whether it is possible to construct the target array starting from an array of all ones by applying the allowed operation zero or more times.

Return `true` if the transformation is possible, otherwise return `false`.

This problem models reverse construction under cumulative constraints and is commonly encountered in system state reconstruction and greedy optimization scenarios.

## Examples

### 1

#### Input

3  
9 3 5

#### Output

YES

#### Explanation

Start with arr = [1, 1, 1]

- Sum = 3, replace index 1 → [1, 3, 1]  
- Sum = 5, replace index 2 → [1, 3, 5]  
- Sum = 9, replace index 0 → [9, 3, 5]  

The target array is successfully constructed.

### 2

#### Input

4  
1 1 1 2

#### Output

NO

#### Explanation

There is no sequence of valid operations that can transform [1, 1, 1, 1] into the target array.

### 3

#### Input

2  
8 5

#### Output

YES

#### Explanation

The target array can be constructed by repeatedly replacing one element with the current sum.

## Input Format

- First line contains an integer n, the length of the target array.
- Second line contains n space-separated integers representing the target array.

## Output Format

- Return true if the target array can be constructed, otherwise return false.

## Constraints

- 1 ≤ n ≤ 50000  
- 1 ≤ target[i] ≤ 10^9  

## Time Limit

1 second

## Memory Limit

512 MB


## Tags

array  

## Company 

quora
