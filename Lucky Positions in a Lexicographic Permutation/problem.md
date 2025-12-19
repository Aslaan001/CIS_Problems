## Title
Lucky Positions in a Lexicographic Permutation

## Slug
lucky-positions-in-a-lexicographic-permutation

## Difficulty
Hard

## Description
A mathematician is fascinated by lucky numbers.  
A lucky number is defined as a positive integer whose decimal representation contains only the digits 4 and 7.

The mathematician considers all permutations of the integers from 1 to n, ordered in lexicographical (dictionary) order.

Given an integer k, the mathematician looks at the k-th permutation in this lexicographical ordering.  
If such a permutation does not exist, the process stops immediately.

Otherwise, for the obtained permutation a, the mathematician wants to analyze special positions.  
A position i is considered special if:
- The index i itself is a lucky number, and
- The value ai at that position is also a lucky number.

Your task is to determine how many such special positions exist in the k-th lexicographical permutation of numbers from 1 to n.

## Examples

### 1
#### Input
7 4  

#### Output
1  

#### Explanation
The 4th lexicographical permutation of numbers from 1 to 7 is:
1 2 3 4 6 7 5  

Only position 4 satisfies the condition that both the index and the value are lucky numbers.

### 2
#### Input
4 7  

#### Output
1  

#### Explanation
The 7th lexicographical permutation of numbers from 1 to 4 is:
2 1 3 4  

Only position 4 satisfies the required condition.

## Input Format
- The input contains two integers n and k:
  - n — the number of elements in the permutation
  - k — the lexicographical index of the permutation

## Output Format
- If the k-th permutation of numbers from 1 to n does not exist, output `-1`.
- Otherwise, output a single integer — the number of positions i such that both i and ai are lucky numbers.

## Constraints
- 1 ≤ n ≤ 10^9  
- 1 ≤ k ≤ 10^9  

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
maths, greedy, hackwithinfy

## Company
infosys
