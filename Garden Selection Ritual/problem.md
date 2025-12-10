## Title
Garden Selection Ritual

## Slug
garden-selection-ritual

## Difficulty
Hard

## Description
A long garden contains n flowers arranged from left to right.  
Each flower has a beauty value ai.

A collector wishes to take exactly m flowers while walking strictly from the left end toward the right.  
When he reaches any flower, he may either take it or ignore it.  
However, the i-th flower he chooses must have beauty at least bi.

Before he begins collecting, he may optionally perform a magical enhancement exactly once:  
he may create a single new flower of any integer beauty k, and insert it at any position in the garden  
(before the first flower, after the last flower, or between existing flowers).

Your task is to determine the smallest integer k such that, after inserting this new flower,  
it becomes possible to collect m flowers in valid order.  
If the collector can already meet the requirements with no added flower, return 0.  
If no choice of k can make the task possible, return −1.

## Examples

### 1
#### Input
9 5  
3 5 2 3 3 5 8 1 2  
4 6 2 4 6

#### Output
6

### 2
#### Input
6 3  
1 2 6 8 2 1  
5 4 3

#### Output
3

## Input Format  
A line with integers n and m  
A line with n integers a1 … an representing beauty values  
A line with m integers b1 … bm representing required minimum beauty for each chosen flower

## Output Format
For every test case, Return the minimum integer k that guarantees a valid collection of m flowers.  
If no additional flower is needed, Return 0.  
If creating any flower cannot help, Return −1.

## Constraints  
1 ≤ m ≤ n ≤ 2×10⁵  
1 ≤ ai ≤ 10⁹  
1 ≤ bi ≤ 10⁹  
Sum of all n across test cases ≤ 2×10⁵

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
dp,BinarySearch,hackwithinfy.

## Company
infosys
