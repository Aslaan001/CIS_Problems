## Title
Balanced Split Sequences

## Slug
balanced-split-sequences

## Difficulty
Hard

## Description

You are given an array of positive integers.  
For each position i, we want to divide nums[i] into two non-negative values arrA[i] and arrB[i] such that:

- arrA forms a non-decreasing sequence from left to right.  
- arrB forms a non-increasing sequence from left to right.  
- arrA[i] + arrB[i] equals nums[i] for every index i.

A pair of sequences (arrA, arrB) that satisfies these rules is called a balanced split.

Your task is to compute how many balanced splits exist for the given array.  
Return the answer modulo 1e9 + 7.

## Examples

### 1

#### Input

3  
2 3 2

#### Output
4

### 2

#### Input

4  
5 5 5 5

#### Output
126

## Input Format

- First line: integer n — the length of the array.  
- Second line: n integers nums[i].  

## Output Format

- Return a single integer — the number of valid balanced split pairs modulo 1e9 + 7.

## Constraints

- 1 ≤ n ≤ 2000  
- 1 ≤ nums[i] ≤ 1000  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

dp combinatorics
