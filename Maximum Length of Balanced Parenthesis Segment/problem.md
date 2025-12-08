## Title
Maximum Length of Balanced Parenthesis Segment

## Slug
maximum-balanced-parenthesis-segment

## Difficulty
Hard

## Description

You are given a string s made up of the characters '(' and ')'.

A balanced segment is a contiguous part of the string that forms a correct parenthesis expression, meaning every opening parenthesis has a matching closing parenthesis in the proper order.

Your task is to compute the length of the longest balanced segment that appears in s.

If no balanced segment exists, the answer is 0.

## Examples

### 1

#### Input
(() 

#### Output
2

### 2

#### Input
)()())

#### Output
4

### 3

#### Input
)

#### Output
0

## Input Format

A single string s.

## Output Format

Return one integer — the maximum length of any balanced parenthesis segment.

## Constraints

0 ≤ |s| ≤ 30000  
Characters in s are '(' or ')'

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
stack, dynamic-programming, two-pointers

