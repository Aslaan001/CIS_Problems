## Title
Dinner Without Disputes

## Slug
dinner-without-disputes

## Difficulty
Hard

## Description
Monocarp is hosting a small dinner party and has prepared n different dishes, arranged in a row.  
Each dish i contains ai portions of food and is labeled using uppercase letters starting from A.

Monocarp also knows m guests, and each guest has specific dishes they enjoy.  
He plans to invite exactly two guests to the dinner.

Once the guests arrive, every dish is handled as follows:

- If neither of the invited guests likes a dish, Monocarp eats all its portions.
- If exactly one of the invited guests likes a dish, that guest eats all its portions.
- If both invited guests like the dish:
  - If the number of portions is even, they split it evenly.
  - If the number of portions is odd, the guests argue over the extra portion, which Monocarp wants to avoid.

A pair of guests is considered valid only if no dish causes an argument.

For every possible value k from 0 to the total number of portions across all dishes, determine how many valid pairs of guests Monocarp can invite such that:
- No argument occurs
- Monocarp ends up eating exactly k portions

Because the number of possibilities can be large, output the result for all k.

## Examples

### 1
#### Input
3 6  
A AB ABC AB BC C  
2 3 5  

#### Output
4 0 0 1 0 2 0 0 0 0 0

## Input Format
- First line: two integers n and m  
- Second line: m strings, where each string represents the set of dishes liked by a guest  
- Third line: n integers representing the number of portions in each dish  

Each string contains distinct uppercase letters and is sorted lexicographically.

## Output Format
Return ∑ai + 1 integers.  
The k-th integer (starting from k = 0) represents the number of valid guest pairs such that Monocarp eats exactly k portions.

## Constraints
1 ≤ n ≤ 20  
2 ≤ m ≤ 5⋅10⁵  
1 ≤ ai ≤ 2⋅10⁴  

## Time Limit
8 seconds

## Memory Limit
512 megabytes

## Tags
recursion, hackwithinfy

## Company
infosys
