## Title
Maximum Reachable Indices with Restricted Jumps

## Slug
maximum-reachable-indices

## Difficulty
Hard

## Description

You are given an array of integers `arr`, where each element represents a platform height, and an integer `d` representing the maximum jump distance.

From an index `i`, you may move:

- to the right: `i + x` such that `1 ≤ x ≤ d` and `i + x < n`
- to the left: `i - x` such that `1 ≤ x ≤ d` and `i - x ≥ 0`

A jump from index `i` to index `j` is allowed only if:

1. `arr[i] > arr[j]`
2. For every index `k` strictly between `i` and `j`,  
   `arr[k] < arr[i]`

You may start from any index in the array.

Your goal is to determine the `maximum number of distinct indices` that can be visited in a valid sequence of jumps.

## Examples

## 1

#### Input

11
6 4 14 6 8 13 9 7 10 6 12
2

#### Output

4

#### Explanation

Starting from value 14 (index 2), you can jump to smaller heights within distance 2.
You can reach indices: 2 → 1 → 0 and 2 → 3.
Total reachable = 4.

## 2

#### Input

5
3 3 3 3 3
3

#### Output

1

#### Explanation

All values are equal, so arr[i] > arr[j] is never true.
No jumps possible.
Maximum reachable = 1 (stay where you start).

## Example 3

#### Input

7
7 6 5 4 3 2 1
1

#### Output

7

#### Explanation

Strictly decreasing, and jump distance = 1.
You can keep moving to the next smaller value.
You can visit all indices.
Total = 7.

## Input Format

- The first line contains an integer `n` — the length of the array.
- The second line contains `n` space-separated integers (`arr[i]`).
- The third line contains the integer `d`.

## Output Format

Return a single integer — the `maximum number of reachable indices`.

## Constraints

1 ≤ n ≤ 1000  
1 ≤ arr[i] ≤ 100000  
1 ≤ d ≤ n  

## Time Limit
`1 second`

## Memory Limit
`512 MB`

## Tags
dynamic-programming, depth-first-search, graph


## Company
hackwithinfy
