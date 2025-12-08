## Title
Evaluate Nested Bracket Score

## Slug
evaluate-nested-bracket-score

## Difficulty
Medium

## Description

You are given a balanced bracket string s containing only the characters '(' and ')'.

Each pair of brackets contributes to the total score according to these rules:

1. A simple pair "()" has a score of 1.  
2. If the string is formed by concatenating two balanced parts A and B, then the total score is score(A) + score(B).  
3. If a balanced part A is wrapped inside a pair of brackets like "(A)", then its score becomes 2 * score(A).

Your task is to compute the total score of the given balanced string s.

## Examples

### 1

#### Input
()

#### Output
1

### 2

#### Input
(())

#### Output
2

### 3

#### Input
()()

#### Output
2

## Input Format

A single balanced bracket string s.

## Output Format

Return one integer — the computed score of the string.

## Constraints

2 ≤ |s| ≤ 50  
Characters in s are '(' and ')'  
The string is guaranteed to be balanced  

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
stack, parsing, recursion


