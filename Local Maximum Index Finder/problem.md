## Title

Local Maximum Index Finder

## Slug

local-maximum-index-finder

## Difficulty

Medium

## Description

A performance monitoring system records a sequence of numerical measurements over time.  
Each measurement is stored in an array `nums`, where adjacent values are guaranteed to be different.

A position `i` in the array is considered a valid peak if the value at that position is strictly greater than its immediate neighbors.

For boundary conditions, assume that the values outside the array are negative infinity.  
This means:
- The first element is compared only with its right neighbor.
- The last element is compared only with its left neighbor.

Your task is to identify any one index that corresponds to a peak element.

If multiple peak positions exist, returning the index of any one of them is acceptable.

To ensure efficiency at scale, your solution must run in logarithmic time complexity.

This problem models scenarios such as signal spike detection, performance anomaly identification, and trend reversal analysis.

## Examples

### 1

#### Input

4  
1 2 3 1

#### Output

2

#### Explanation

The value 3 is greater than both of its neighbors, so index 2 is a valid peak.

### 2

#### Input

7  
1 2 1 3 5 6 4

#### Output

5

#### Explanation

There are two valid peaks:
- Index 1 with value 2  
- Index 5 with value 6  

Either index is a valid answer.

## Input Format

- First line contains an integer n, the number of elements in the array.
- Second line contains n space-separated integers representing the array nums.

## Output Format

- Return a single integer representing the index of any peak element.

## Constraints

- 1 ≤ n ≤ 1000  
- -2^31 ≤ nums[i] ≤ 2^31 - 1  
- nums[i] is not equal to nums[i + 1] for all valid i

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

array  

## Company 

snapchat