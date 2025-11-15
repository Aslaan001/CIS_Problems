## Title

Balance Pivot Finder

## Slug

pivot-index

## Difficulty

Easy

## Description

You are given an array `nums` representing loads distributed across stations in a line.  
A `balance pivot` is an index where the sum of all loads strictly to its left is equal to the sum of all loads strictly to its right.

If the pivot lies at an edge, the missing side is treated as having a sum of 0.

Your task is to return the `leftmost` such balance pivot.  
If no balance point exists, return `-1`.

## Examples

### 1

#### Input

nums = [1, 7, 3, 6, 5, 6]

#### Output

3

### 2

#### Input

nums = [1, 2, 3]

#### Output

-1

### 3

#### Input

nums = [2, 1, -1]

#### Output

0

## Input Format

- A single line containing an integer array `nums`.

## Output Format

- Return the index representing the leftmost pivot, or -1 if no such pivot exists.

## Constraints

- 1 ≤ nums.length ≤ 10⁴
- -1000 ≤ nums[i] ≤ 1000

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

array, prefix-sum
