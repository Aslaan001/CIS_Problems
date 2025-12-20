## Title

Cyclic Log Rotation Analysis

## Slug

cyclic-log-rotation-analysis

## Difficulty

Hard

## Description

A distributed monitoring system stores event logs as a continuous string of characters. Due to load balancing and replication strategies, the system periodically performs cyclic rotations on the log string to redistribute data across nodes.

You are given two strings `s` and `t`, both of equal length `n`, representing the initial log sequence and the desired final log sequence respectively. You are also given an integer `k`, representing the exact number of rotation operations that must be performed.

In one rotation operation, the system performs the following action on string `s`:

Remove a suffix of `s` of length `l`, where `0 < l < n`, and append it to the beginning of `s`.

Formally, if `s = prefix + suffix`, the operation transforms `s` into `suffix + prefix`.

Your task is to determine the number of distinct ways in which the initial log string `s` can be transformed into the target log string `t` using exactly `k` such operations.

Each operation is considered distinct based on the chosen suffix length, even if it results in the same intermediate string.

Since the number of valid transformation sequences can be very large, return the result modulo `10^9 + 7`.

## Examples

### 1

#### Input
abcd  
cdab  
2

#### Output
2

#### Explanation

There are two valid sequences of operations that transform `s` into `t` in exactly two steps.

### 2

#### Input
ababab  
ababab  
1

#### Output
2

#### Explanation

Two different suffix choices result in the same string, but are counted as separate operations.

## Input Format

- First line: string `s`
- Second line: string `t`
- Third line: integer `k`

## Output Format

- Return a single integer — the number of valid transformation sequences modulo `10^9 + 7`

## Constraints

- 2 ≤ n ≤ 5 × 10^5
- 1 ≤ k ≤ 10^15
- `s.length == t.length`
- `s` and `t` consist only of lowercase English letters

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

dynamic-programming  
