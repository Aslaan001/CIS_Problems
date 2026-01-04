## Title  
Certified Range Compliance Subarrays  

## Slug  
certified-range-compliance-subarrays  

## Difficulty  
Medium  

## Description  

An enterprise monitoring platform logs numerical readings from a continuous data stream. Each reading represents a measured system value captured at a specific time interval.

You are given an integer array nums, where each element corresponds to a recorded reading, and an integer k representing an allowed tolerance threshold defined by compliance rules.

Some readings are classified as certified values. A value is considered certified if it is a prime number, meaning it is greater than 1 and divisible only by 1 and itself.

A subarray of nums is said to be range-compliant if it satisfies the following conditions:

- It contains at least two certified (prime) values.
- The difference between the maximum and minimum certified values in that subarray is less than or equal to k.

Your task is to determine how many such range-compliant subarrays exist in nums.

Only the certified values within a subarray are considered when evaluating the range constraint.

## Examples  

### 1  

#### Input  
3  
1 2 3  
1  

#### Output  
2  

#### Explanation  
The valid range-compliant subarrays are:  
[2, 3] and [1, 2, 3].  

Both subarrays contain the certified values 2 and 3, and their difference is 1, which is within the allowed threshold.  

### 2  

#### Input  
4  
2 3 5 7  
3  

#### Output  
4  

#### Explanation  
The range-compliant subarrays are:  
[2, 3], [2, 3, 5], [3, 5], and [5, 7].  

Each subarray contains at least two certified values, and the maximum difference among them does not exceed 3.  

## Input Format  

- The first line contains an integer n — the number of recorded readings.  
- The second line contains n space-separated integers representing the readings.  
- The third line contains an integer k — the maximum allowed range threshold.  

## Output Format  

Return a single integer — the total number of range-compliant subarrays in nums.  

## Constraints  

1 ≤ n ≤ 50000  
1 ≤ nums[i] ≤ 50000  
0 ≤ k ≤ 50000  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

array, queue.
