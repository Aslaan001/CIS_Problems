## Title  
Longest Stable Sensor Readings Window  

## Slug  
longest-stable-sensor-readings-window  

## Difficulty  
Medium  

## Description  

A monitoring system continuously records numerical readings from a sensor and stores them in an array.  
Due to operational constraints, a segment of readings is considered stable only if the difference between the highest and lowest values within that segment does not exceed a given tolerance limit.

You are given:
- An integer array nums representing sensor readings recorded over time.
- An integer limit representing the maximum allowed difference between any two readings within a stable segment.

A segment (subarray) is defined as a contiguous sequence of readings.

Your task is to determine the length of the longest non-empty contiguous segment such that the absolute difference between any two values in that segment is less than or equal to limit.

## Examples  

### 1  

#### Input  
4  
8 2 4 7  
4  

#### Output  
2  

#### Explanation  

The longest stable segments are [2, 4] and [4, 7], each having a maximum difference within the allowed limit.

### 2  

#### Input  
6  
10 1 2 4 7 2  
5  

#### Output  
4  

#### Explanation  

The segment [2, 4, 7, 2] has a maximum difference of 5, which satisfies the limit, and has the maximum possible length.

### 3  

#### Input  
8  
4 2 2 2 4 4 2 2  
0  

#### Output  
3  

#### Explanation  

With a zero tolerance limit, only segments with identical values are valid.  
The longest such segment has length 3.

## Input Format  

- The first line contains an integer n — the number of sensor readings  
- The second line contains n space-separated integers representing the readings  
- The third line contains an integer limit  

## Output Format  

Return a single integer representing the length of the longest stable contiguous segment.

## Constraints  

1 ≤ n ≤ 100000  
1 ≤ nums[i] ≤ 1000000000  
0 ≤ limit ≤ 1000000000  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

queue.
