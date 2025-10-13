## Title

Deepest Leaves Sum


## Slug

deepest-leaves-sum

## Difficulty

Medium

## Description

In the mystical forest , An ancient `Tree of Life` grows — each node of the tree holds a number representing the life energy of that part of the forest.  

Your task, as the `Forest Sage`, is to find the `sum of values of the deepest leaves` in the tree — the leaves that lie at the greatest depth.

## Examples

### 1

#### Input

13
1 2 3 4 5 null 6 7 null null null null 8

#### Output

15

#### Explanation

The deepest leaves are `[7, 8]`.  
Their sum is `7 + 8 = 15`.

### 2

#### Input

15
6 7 8 2 7 1 3 9 null 1 4 null null null 5

#### Output

19

#### Explanation

The deepest leaves have values `[9, 1, 4, 5]`.  
Their sum is `9 + 1 + 4 + 5 = 19`.  

## Input Format  


- First line: integer `n` — number of nodes in the binary tree  
- Second line: `n` space-separated values representing the level-order traversal of the tree  
  (use `null` for missing nodes)

## Output Format  

- Return the `smallest rune` that is lexicographically greater than the target.  
- If no such rune exists, return the `first rune` in the sequence.  



## Constraints  

- 2 ≤ n ≤ 1e5  
- Each rune is a lowercase English letter (`'a'` to `'z'`).  
- The list contains at least two distinct runes. 

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

binary-search, arrays, strings. 
