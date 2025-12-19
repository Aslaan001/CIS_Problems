## Title
Counting Tall Binary Search Trees

## Slug
counting-tall-binary-search-trees

## Difficulty
Hard

## Description
A systems researcher is studying different configurations of binary search trees built from a fixed set of keys.

You are given a positive integer n, representing the number of distinct keys labeled from 1 to n.  
Using these keys, all possible binary search trees (BSTs) can be constructed, where each key appears exactly once.

A binary search tree follows these rules:
- Each node contains a unique key.
- All keys in the left subtree of a node are smaller than the node’s key.
- All keys in the right subtree of a node are larger than the node’s key.
- Each node may have zero, one, or two children.

The height of a binary search tree is defined as the maximum number of nodes on a path from the root to any leaf, counting both the root and the leaf.

Among all possible binary search trees with n nodes, some trees have greater height than others.  
Your task is to determine how many distinct binary search trees with n nodes have a height of at least h.

Each valid tree configuration is counted separately.

## Examples

### 1
#### Input
3 2  

#### Output
5  

#### Explanation
There are 5 distinct binary search trees with 3 nodes whose height is at least 2.

### 2
#### Input
3 3  

#### Output
4  

#### Explanation
Out of all possible binary search trees with 3 nodes, 4 have height at least 3.

## Input Format
- The input contains two space-separated integers n and h.

## Output Format
Return a single integer — the number of binary search trees with n nodes whose height is not less than h.

## Constraints
- 1 ≤ n ≤ 35  
- 1 ≤ h ≤ n  
- The answer does not exceed 9 × 10^18  

## Time Limit
1 second

## Memory Limit
64 megabytes

## Tags
maths, hackwithinfy

## Company
infosys
