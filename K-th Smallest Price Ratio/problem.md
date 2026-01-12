## Title  
K-th Smallest Price Ratio  

## Slug  
kth-smallest-prime-fraction  

## Difficulty  
Medium  

## Description  

A financial analytics system tracks price benchmarks using a sorted list of unique values.  
The list always starts with 1, followed by increasing prime numbers.

From this list, analysts generate ratios by dividing one value by another value that appears later in the list.  
Formally, for every pair of indices i and j such that 0 ≤ i < j < n, a ratio is formed as:

arr[i] / arr[j]

All such ratios are considered and sorted in ascending order.

Given:
- A sorted integer array arr containing 1 and prime numbers
- An integer k

Your task is to determine the k-th smallest ratio and return it as a pair of integers  
[arr[i], arr[j]] representing the numerator and denominator of that ratio.

## Examples  

### 1  

#### Input  
4  
1 2 3 5  
3  

#### Output  
2 5  

#### Explanation  

All possible ratios in ascending order are:  
1/5, 1/3, 2/5, 1/2, 3/5, 2/3  

The 3rd smallest ratio is 2/5.

### 2  

#### Input  
2  
1 7  
1  

#### Output  
1 7  

## Input Format  

- The first line contains an integer n — the length of the array  
- The second line contains n space-separated integers representing the array arr  
- The third line contains an integer k  

## Output Format  

Return two integers — the numerator and denominator of the k-th smallest ratio.

## Constraints  

2 ≤ n ≤ 1000  
1 ≤ arr[i] ≤ 30000  
arr[0] = 1  
arr[i] is prime for i > 0  
All elements of arr are unique and sorted  
1 ≤ k ≤ n × (n − 1) / 2  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

priority-queue.