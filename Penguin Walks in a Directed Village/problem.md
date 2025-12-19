## Title
Penguin Walks in a Directed Village

## Slug
penguin-walks-in-a-directed-village

## Difficulty
Hard

## Description
A small village consists of n houses arranged in a line and indexed from 1 to n.  
Each house has a plaque displaying an integer between 1 and n.

A penguin enjoys walking through the village in a deterministic way.  
If the penguin is currently standing at house x, he moves next to the house whose number is written on the plaque of house x.  
He continues walking in this manner indefinitely.

The village must satisfy the following conditions:

- If the penguin starts walking from any house with index between 1 and k (inclusive), he is able to reach house 1 at some point.
- If the penguin starts walking from any house with index between k + 1 and n (inclusive), he is guaranteed to never reach house 1.
- If the penguin starts walking from house 1, after a positive number of moves, he can return to house 1 again.

Your task is to determine the number of different ways to assign numbers to the plaques of all houses such that all the conditions above are satisfied.

Since the answer can be large, output it modulo 10^9 + 7.

## Examples

### 1
#### Input
5 2  

#### Output
54  

#### Explanation
There are 54 different valid ways to assign plaque numbers so that the walking conditions are satisfied.

### 2
#### Input
7 4  

#### Output
1728  

#### Explanation
All assignments counted ensure that houses 1 through 4 can reach house 1, while houses 5 through 7 cannot.

## Input Format
- The input contains two space-separated integers n and k:
  - n — the total number of houses
  - k — the number of starting houses that must be able to reach house 1

## Output Format
Return a single integer — the number of valid plaque assignments modulo 10^9 + 7.

## Constraints
- 1 ≤ n ≤ 1000  
- 1 ≤ k ≤ min(8, n)  

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
maths, greedy, hackwithinfy

## Company
infosys
