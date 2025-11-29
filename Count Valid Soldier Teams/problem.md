## Title
Count Valid Soldier Teams

## Slug
count-valid-soldier-teams

## Difficulty
Medium

## Description
You are given an array of unique integers representing the rating of soldiers standing in a line.

Your task is to count how many valid teams of three soldiers can be formed.  
A team consists of indices (i, j, k) such that 0 ≤ i < j < k < n, and the ratings must satisfy one of the following:

- rating[i] < rating[j] < rating[k]  
- rating[i] > rating[j] > rating[k]

A soldier may be part of multiple teams.

Return the total number of valid teams.

## Examples

### 1
#### Input
5  
2 5 3 4 1

#### Output
3

#### Explanation
Valid teams are:  
(2, 3, 4), (5, 4, 1), (5, 3, 1)

### 2
#### Input
3  
2 1 3

#### Output
0

### 3
#### Input
4  
1 2 3 4

#### Output
4

## Input Format
- The first line contains an integer n  
- The second line contains n space-separated unique integers representing ratings

## Output Format
Return a single integer — the total number of valid teams.

## Constraints
3 ≤ n ≤ 1000  
1 ≤ rating[i] ≤ 100000  
All ratings are unique

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
array, counting, combinatorics, dp

## Company
hackwithinfy