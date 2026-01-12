## Title  
Fastest Data Window Reaching Target Load  

## Slug  
shortest-subarray-with-sum-at-least-k  

## Difficulty  
Hard  

## Description  

A data processing system continuously records numerical values representing workload changes over time.  
Engineers need to analyze this stream to detect the fastest time window in which the accumulated workload reaches or exceeds a required target.

You are given:
- An integer array nums, where each value represents the workload change at a specific time step (values can be positive or negative).
- An integer k, representing the minimum required total workload.

A window (subarray) is defined as a contiguous sequence of values in nums.

Your task is to determine the length of the shortest non-empty subarray whose sum is at least k.  
If no such subarray exists, return -1.

## Examples  

### 1  

#### Input  
1  
1  
1  

#### Output  
1  

### 2  

#### Input  
2  
1 2  
4  

#### Output  
-1  

### 3  

#### Input  
3  
2 -1 2  
3  

#### Output  
3  

## Input Format  

- The first line contains an integer n — the number of time steps  
- The second line contains n space-separated integers representing nums  
- The third line contains an integer k  

## Output Format  

Return a single integer — the length of the shortest valid subarray.  
If no such subarray exists, return -1.

## Constraints  

1 ≤ n ≤ 100000  
-100000 ≤ nums[i] ≤ 100000  
1 ≤ k ≤ 1000000000  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

queue.
