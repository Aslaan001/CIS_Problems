## Title

Delete and Earn

## Slug

delete-and-earn

## Difficulty

Medium

## Description

You are given an integer array `nums`. You want to maximize the number of points you can earn by performing the following operation any number of times:

Pick any `nums[i]` and delete it to earn `nums[i]` points. Afterwards, you must delete every element equal to `nums[i] - 1` and every element equal to `nums[i] + 1`.

Return the maximum number of points you can earn.

## Examples

### 1

#### Input

nums = [3, 4, 2]

#### Output

6

### 2

#### Input

nums = [2, 2, 3, 3, 3, 4]

#### Output

9

## Input Format

- A single line containing an integer array `nums`.

## Output Format

- Return a single integer representing the maximum points obtainable.

## Constraints

- 1 ≤ nums.length ≤ 2 × 10^4
- 1 ≤ nums[i] ≤ 10^4

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

dynamic-programming, array, greedy
