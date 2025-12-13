## Title
The Crystal Vault Selection

## Slug
the-crystal-vault-selection

## Difficulty
Hard

## Description
Deep inside an underground vault lies a perfect cubic chamber made of crystal cells.  
The chamber has n layers, each layer containing an n × n grid of crystal values, forming a complete n × n × n cube.

An explorer wants to collect exactly n crystals from this vault such that the total collected value is as small as possible.

However, the vault has strict stability rules.  
Each crystal is identified by three coordinates (x, y, z), and the explorer must obey the following restriction:

It is forbidden to select two crystals that lie in the same vertical slice, horizontal slice, or depth slice.  
In other words, no two selected crystals may share the same x-coordinate, the same y-coordinate, or the same z-coordinate.

Your task is to determine the minimum possible sum of values of n crystals that can be selected while respecting these constraints.

## Examples

### 1
#### Input
3  
1 2 3  
4 5 6  
7 8 9  
1 1 1  
2 2 2  
3 3 3  
4 3 0  
2 1 4  
9 8 9  

#### Output
5

## Input Format
- The first line contains a single integer n.  
- The next n² lines each contain n integers.  

The values are given layer by layer.  
For coordinates (x, y, z), the value at that position is the z-th number in the ((x−1) × n + y)-th line.

## Output Format
Return a single integer — the minimum possible sum of the selected crystals.

## Constraints
2 ≤ n ≤ 12  
0 ≤ value ≤ 2 × 10⁷  

## Time Limit
3 seconds

## Memory Limit
1024 megabytes

## Tags
recursion, hackwithinfy

## Company
infosys
