## Title
Boulders on the Trail

## Slug
boulders-on-the-trail

## Difficulty
Hard

## Description
To prepare her "Takodachi" dumbo octopuses for world domination, Ina of the Mountain orders Hoshimachi Suisei to throw boulders at them.  
There is a single-file line of n octopuses standing on a trail, numbered from 1 to n. The i-th octopus currently has health ai (1 ≤ ai ≤ k).

Each boulder crushes a contiguous group of octopuses with indices l, l+1, …, r (1 ≤ l ≤ r ≤ n). When a boulder hits, the health of each crushed octopus is decreased by 1. However, octopuses are peculiar: if an octopus's health becomes 0, it immediately regenerates to k.

Your task is to choose the minimum number of boulders (each described by some interval [l, r]) so that after all throws, every octopus ends up with health equal to k.

Compute the minimum number of boulders required.

## Examples

### 1
#### Input
4 3  
1 2 1 3

#### Output
2

#### Explanation
Throw on [1,3] → health becomes [3,1,3,3]  
Throw on [2,2] → health becomes [3,3,3,3]

### 2
#### Input
7 3  
1 2 3 1 3 2 1

#### Output
4

#### Explanation
One optimal sequence of intervals is [1,7], [2,6], [3,5], [4,4].

## Input Format
- The first line contains two integers n and k — the number of octopuses and the regeneration threshold.  
- The second line contains n integers a1, a2, …, an — the initial health values.

## Output Format
Return a single integer — the minimum number of boulders needed so that every octopus has health equal to k after all throws.

## Constraints 
1 ≤ n ≤ 2·10^5 (sum of n over all test cases ≤ 2·10^5)  
1 ≤ k ≤ 10^9  
1 ≤ ai ≤ k

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
dynamic-programming, greedy, hackwithinfy

## Company
infosys
