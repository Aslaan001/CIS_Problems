## Title

Maximize Pairwise GCD Score

## Slug

maximize-pairwise-gcd-score

## Difficulty

Hard

## Description

You are given an array nums of length 2 * n.  
You must perform n operations on this array.

In the i-th operation (1-indexed):

- Choose two unused elements x and y  
- Gain a score equal to i * gcd(x, y)  
- Remove x and y from the array  

Your task is to determine the maximum score achievable after all n operations.

## Examples

### 1

#### Input
1
1 2

#### Output
1

#### Explanation

Only one pair exists.  
Score = 1 * gcd(1, 2) = 1.

### 2

#### Input
2
3 4 6 8

#### Output
11

#### Explanation

One optimal pairing is:  
(1 * gcd(3, 6)) + (2 * gcd(4, 8)) = 3 + 8 = 11.

### 3

#### Input
3
1 2 3 4 5 6

#### Output
14

#### Explanation

An optimal selection is:  
(1 * gcd(1, 5))  
+ (2 * gcd(2, 4))  
+ (3 * gcd(3, 6))  
= 14.

## Input Format

- Array nums of size 2 * n
- All integers are positive

## Output Format

- Return the maximum total score after performing n operations

## Constraints

- 1 ≤ n ≤ 7  
- nums.length = 2 * n  
- 1 ≤ nums[i] ≤ 10^6  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

BitmaskDP,Combinatorics
