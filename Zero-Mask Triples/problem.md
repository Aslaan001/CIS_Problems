## Title

Zero-Mask Triples

## Slug

zero-mask-triples

## Difficulty

Hard

## Description

You are given an array of non-negative integers.  
Your task is to count how many ordered triples of indices (i, j, k) satisfy:

- `0 ≤ i < n`  
- `0 ≤ j < n`  
- `0 ≤ k < n`  
- `(nums[i] & nums[j] & nums[k]) == 0`

Here `&` represents the bitwise AND operator.

Return the total number of such triples.

## Examples

### 1

#### Input

3  
2 1 3

#### Output
12

#### Explanation

There are `3 × 3 × 3 = 27` ordered triples.  
Among them, 12 triples produce a bitwise AND equal to zero.

### 2

#### Input

3  
0 0 0

#### Output

27

#### Explanation

Every triple results in `0 & 0 & 0 = 0`.  
So all 27 triples are valid.

## Input Format

- First line: integer `n` — number of elements.  
- Second line: `n` integers `nums[i]`.

## Output Format

- Return a single integer — the number of valid AND triples.

## Constraints

- 1 ≤ n ≤ 1000  
- 0 ≤ nums[i] < 2¹⁶  
- Result fits in 64-bit integer.

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

dynamic-programming
