## Title
Reconstructing a Hidden Painting Process

## Slug
reconstruct-hidden-painting-process

## Difficulty
Hard

## Description
You are observing a strange painting machine that colors n cells arranged in a line from left to right.  
All cells start white, and each has an internal score initially equal to 0.

The machine follows a secret order p (a permutation of 1…n). It performs n operations:

At operation i (1 ≤ i ≤ n):
1. If i > 1:
     Let x = p[i]. Among all already blackened cells, locate the one whose position is closest to x  
     (ties are broken by choosing the smaller index).
     Increase the score of that closest black cell by 1.
2. Then the machine colors the cell at position p[i] black.

After all operations finish, each cell ends up with a final score.  
These scores form an array s of length n.

You are given s, but some positions may contain -1, meaning their score is unknown.  
Determine how many permutations p are able to produce a final score array that matches the given partial information.

Return the number of valid permutations modulo 998244353.

## Examples

### 1
#### Input
3
-1 -1 1
#### Output
2

### 2
#### Input
3
-1 -1 -1
#### Output
6

### 3
#### Input
4
-1 2 -1 0
#### Output
4

## Input Format
A single integer n  
A line of n integers representing the array s, where si = -1 or 0 ≤ si < n.

## Output Format
Return the number of permutations that could generate a compatible score sequence.

## Constraints
2 ≤ n ≤ 100  
-1 ≤ si ≤ n − 1  
Sum of n² across all test cases ≤ 10000

## Time Limit
3000

## Memory Limit
512

## Tags
combinatorics,dp,hackwithinfy.

## Company
infosys
