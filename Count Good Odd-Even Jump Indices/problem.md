## Title
Count Good Odd-Even Jump Indices

## Slug
count-good-odd-even-jump-indices

## Difficulty
Hard

## Description

You are given an integer array arr of length n.

From a starting index i, you can perform a sequence of jumps.  
The 1st, 3rd, 5th, ... jumps are odd-numbered jumps.  
The 2nd, 4th, 6th, ... jumps are even-numbered jumps.

Each jump must move forward to an index j with j > i, following these rules:

Odd-numbered jump:  
Jump to the index j such that arr[i] ≤ arr[j] and arr[j] is the smallest possible among all valid choices.  
If multiple indices have the same value, choose the smallest j.

Even-numbered jump:  
Jump to the index j such that arr[i] ≥ arr[j] and arr[j] is the largest possible among all valid choices.  
If multiple indices have the same value, choose the smallest j.

If at any point no valid jump exists, the sequence stops.

A starting index is considered good if you can reach the last index (n − 1) after performing some number of jumps (possibly zero).

Your task is to compute how many starting indices are good.

## Examples

### 1

#### Input
5  
10 13 12 14 15

#### Output
2

### 2

#### Input
5  
2 3 1 1 4

#### Output
3

### 3

#### Input
5  
5 1 3 4 2

#### Output
3

## Input Format

The first line contains the integer n.  
The second line contains n integers representing arr.

## Output Format

Output a single integer — the number of good starting indices.

## Constraints

1 ≤ n ≤ 2 × 10⁴  
0 ≤ arr[i] < 10⁵

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
dynamic programming, monotonic stack, sorting, greedy

## Company
hackwithinfy
