## Title  
Harmonious Selection Count

## Slug  
harmonious-selection-count

## Difficulty  
Medium

## Description  

You are given a list of positive integers.  
You want to count how many different non-empty selections of these integers can be formed such that no two chosen numbers are spaced exactly k apart in value.

A selection is considered harmonious if for every pair of elements in it, their absolute difference is not equal to k.

Two selections are considered different if they differ by at least one index chosen from the original list.

Your task is to determine how many harmonious selections can be made.

## Examples  

### Example 1

Input  
3  
2 4 6  
2

Output  
4

Explanation  
Valid harmonious selections include:
[2], [4], [6], and [2, 6].

### Example 2

Input  
1  
1  
1

Output  
1

Explanation  
Only one selection is possible.

## Input Format  

- The first line contains an integer n.  
- The second line contains n space-separated integers.  
- The third line contains an integer k.

## Output Format  

Return the total number of non-empty harmonious selections.

## Constraints  

1 ≤ n ≤ 18  
1 ≤ values[i] ≤ 1000  
1 ≤ k ≤ 1000  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

combinatorial counting.
