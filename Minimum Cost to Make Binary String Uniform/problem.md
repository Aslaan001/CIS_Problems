## Title
Minimum Cost to Make Binary String Uniform

## Slug
minimum-cost-make-binary-string-uniform

## Difficulty
Hard

## Description

You are given a binary string s of length n consisting of characters 0 and 1.

You may perform two types of operations:

- Prefix Flip  
  Choose an index i (0 ≤ i < n).  
  Flip all characters from index 0 to index i (inclusive).  
  The cost of this operation is i + 1.

- Suffix Flip  
  Choose an index i (0 ≤ i < n).  
  Flip all characters from index i to index n - 1 (inclusive).  
  The cost of this operation is n - i.

Flipping a character changes:
0 → 1  
1 → 0

Your task is to compute the minimum cost needed to make the entire string uniform, either all 0s or all 1s.

You may perform operations in any order and any number of times.

## Examples

### 1

#### Input
0011

#### Output
2

#### Explanation
A suffix flip at index 2 converts the string to 0000 with a cost of 2.  
This is the minimum possible cost.

### 2

#### Input
010101

#### Output
9

#### Explanation
One optimal sequence is:

i = 2 → prefix flip → cost 3 → 101101  
i = 1 → prefix flip → cost 2 → 011101  
i = 0 → prefix flip → cost 1 → 111101  
i = 4 → suffix flip → cost 2 → 111110  
i = 5 → suffix flip → cost 1 → 111111  

Total cost = 9.

## Input Format

- A single binary string s.

## Output Format

Return a single integer representing the minimum cost to make all characters equal.

## Constraints

1 ≤ n ≤ 100000  
s[i] ∈ {0, 1}

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
greedy, dynamic-programming, string, prefix-sum

## Company
hackwithinfy
