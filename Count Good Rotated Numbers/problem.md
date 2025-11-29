## Title
Count Good Rotated Numbers

## Slug
count-good-rotated-numbers

## Difficulty
Medium

## Description

You are given an integer n.  
A number in the range [1, n] is considered good if rotating each of its digits by 180 degrees results in:

1. a valid number, and  
2. a number different from the original.

A digit is valid for rotation if:

0, 1, 8 rotate to themselves  
2 and 5 rotate to each other  
6 and 9 rotate to each other  
All other digits become invalid after rotation

Every digit must be rotated; leaving any digit unchanged is not allowed.

Your task is to count how many integers in [1, n] are good.

## Examples

### 1

#### Input
10

#### Output
4

#### Explanation
The good numbers are 2, 5, 6, 9.

### 2

#### Input
1

#### Output
0

### 3

#### Input
2

#### Output
1

## Input Format

The first line contains the integer n.

## Output Format

Return a single integer — the number of good rotated integers in [1, n].

## Constraints

1 ≤ n ≤ 10⁴

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
math, digit dp, enumeration, simulation

## Company
hackwithinfy
