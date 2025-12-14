## Title

Balanced Subset Incompatibility

## Slug

balanced-subset-incompatibility

## Difficulty

Hard

## Description

You are given an integer array `nums` and an integer `k`.  
Your task is to divide all elements of `nums` into exactly `k` groups such that:

- Every group has the same number of elements.  
- No group contains duplicate values.

For any group, its incompatibility is defined as:

max(group) − min(group)

Your goal is to minimize the total incompatibility across all `k` groups.  
If no valid grouping exists, return `-1`.

A group is an unordered collection of integers.

## Examples

### 1

#### Input
4 2
1 2 1 4  

#### Output  
4

#### Explanation

A valid distribution:  
- [1, 2] → incompatibility = 1  
- [1, 4] → incompatibility = 3  

Total = 4.


### 2

#### Input
6 3
5 3 3 6 3 3  

#### Output  
-1

#### Explanation

Each group must contain 2 elements, but duplicates make this impossible.  
Hence return -1.

## Input Format

- Integer array `nums`  
- Integer `k`  
- nums.length is divisible by k  
- 1 ≤ nums.length ≤ 16  
- 1 ≤ nums[i] ≤ nums.length

## Output Format

- Return the minimum total incompatibility, or -1 if no valid grouping exists.

## Constraints

- 1 ≤ nums.length ≤ 16  
- 1 ≤ k ≤ nums.length  
- nums.length % k == 0  
- Answer fits in 32-bit signed integer

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

dynamic-programming
