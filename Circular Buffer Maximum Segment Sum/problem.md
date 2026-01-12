## Title  
Circular Buffer Maximum Segment Sum  

## Slug  
circular-buffer-maximum-segment-sum  

## Difficulty  
Medium  

## Description  

A monitoring system stores numerical readings in a circular buffer. The buffer wraps around such that the element after the last index connects back to the first index.

You are given an integer array nums of length n representing the values stored in this circular buffer.

A segment is defined as a contiguous sequence of elements taken from the buffer, with the following conditions:

- The segment must be non-empty.
- Each buffer position can be used at most once in the segment.
- The segment may wrap around from the end of the array to the beginning due to the circular nature.

Formally, if the segment starts at index i and ends at index j, it includes elements  
nums[i], nums[i + 1], ..., nums[j], where indexing wraps around using modulo n.

Your task is to determine the maximum possible sum of any valid segment in the circular buffer.

## Examples  

### 1  

#### Input  
4  
1 -2 3 -2  

#### Output  
3  

#### Explanation  

The maximum sum segment is [3], which gives a total sum of 3.

### 2  

#### Input  
3  
5 -3 5  

#### Output  
10  

#### Explanation  

The segment wraps around the buffer and includes the first and last elements: [5, 5].  
The sum of this segment is 10.

### 3  

#### Input  
3  
-3 -2 -3  

#### Output  
-2  

#### Explanation  

All values are negative, so the maximum sum segment consists of the single largest value [-2].

## Input Format  

- The first line contains an integer n — the number of elements in the buffer.  
- The second line contains n space-separated integers representing the buffer values.  

## Output Format  

Return a single integer — the maximum possible sum of a valid circular segment.

## Constraints  

1 ≤ n ≤ 30000  
-30000 ≤ nums[i] ≤ 30000  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

queue.
