## Title
Minimum Set Size With Units Digit K

## Slug
minimum-set-size-with-units-digit-k

## Difficulty
Medium

## Description
You are given two integers `num` and `k`.  
Your task is to determine the minimum number of positive integers you can choose such that:

- Each number ends with the digit `k`
- The sum of all chosen numbers equals `num`
- Repetition of numbers is allowed
- The empty set has a total sum of 0

If no such set exists, return `-1`.

## Examples

### 1
#### Input
58 9

#### Output
2

#### Explanation
Valid sets include:  
[9, 49]  
[19, 39]  
Both sum to 58, and the minimum size is 2.

### 2
#### Input
37 2

#### Output
-1

#### Explanation
No combination of numbers ending with digit 2 can sum to 37.

### 3
#### Input
0 7

#### Output
0

#### Explanation
The empty set has sum 0.

## Input Format
- A single line with two integers `num` and `k`.

## Output Format
Return a single integer — the minimum size of the set, or `-1` if no valid set exists.

## Constraints
0 ≤ num ≤ 3000  
0 ≤ k ≤ 9

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
math, greedy, modular-arithmetic

## Company
hackwithinfy
