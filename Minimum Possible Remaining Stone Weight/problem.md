## Title
Minimum Possible Remaining Stone Weight

## Slug
minimum-remaining-stone-weight

## Difficulty
Medium

## Description

You are given an array of positive integers where each value represents the weight of a stone.

A process is defined where, in each move, you select any two stones with weights `x` and `y` such that `x ≤ y`, and smash them together:

- If `x == y`, both stones are removed.
- If `x != y`, the stone with weight `x` is removed, and the stone with weight `y` is replaced by a new stone of weight `y - x`.

The process continues until zero or one stones remain.

Your task is to determine the `smallest possible weight` of the final stone after performing any sequence of valid smash operations.

If all stones can be destroyed, return `0`.

## Examples

### 1

#### Input
6  
2 7 4 1 8 1

#### Output
1

#### Explanation
One optimal sequence of smashes results in ending with a single stone of weight 1.

### 2

#### Input
5  
31 26 33 21 40

#### Output
5

## Input Format

- The first line contains an integer `n`, the number of stones.
- The second line contains `n` space-separated integers representing the stone weights.

## Output Format

Return a single integer — the minimum possible weight of the final stone.

## Constraints

1 ≤ n ≤ 30  
1 ≤ stones[i] ≤ 100  

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
dp, knapsack, partition, subset-sum

## Company
hackwithinfy
