## Title

Count Separate Land Masses

## Slug

count-separate-land-masses

## Difficulty

Medium

## Description

You are given a 2D grid of size m × n containing only the characters '0' and '1'.  
A cell with '1' represents land, and a cell with '0' represents water.

A land mass is defined as a group of land cells that are directly connected by their sides  
(horizontal or vertical adjacency). Diagonal connections do not count.

Your task is to determine how many distinct land masses exist in the grid.  
You may assume that the entire border of the grid is surrounded by water.

## Examples

### 1

#### Input
4 5  
1 1 1 1 0  
1 1 0 1 0  
1 1 0 0 0  
0 0 0 0 0  

#### Output
1

### 2

#### Input
4 5  
1 1 0 0 0  
1 1 0 0 0  
0 0 1 0 0  
0 0 0 1 1  

#### Output
3

## Input Format

- First line: two integers m and n  
- Next m lines: n characters ('0' or '1') representing the grid

## Output Format

- Return a single integer: the number of connected land regions

## Constraints

- 1 ≤ m, n ≤ 300  
- Each grid cell is either '0' or '1'

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

dfs, bfs, graph, flood-fill, grid
