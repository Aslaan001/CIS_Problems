## Title

Landmass Cluster Identification

## Slug

landmass-cluster-identification

## Difficulty

Medium

## Description

A satellite monitoring system captures a binary map of a geographic region to analyze land distribution.  
The map is represented as a 2D grid where each cell contains either:

- `1` indicating land  
- `0` indicating water  

A landmass cluster (island) is defined as a group of land cells connected horizontally or vertically.  
Diagonal connections do not count.

The outer boundary of the grid is guaranteed to be water, ensuring that all land clusters are fully enclosed within the map.

Your task is to analyze the grid and determine the total number of distinct landmass clusters present.

This analysis is commonly used in geographic data processing, environmental modeling, and spatial analytics systems.

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

#### Explanation

All land cells are connected through horizontal or vertical paths, forming a single landmass cluster.

### 2

#### Input

4 5  
1 1 0 0 0  
1 1 0 0 0  
0 0 1 0 0  
0 0 0 1 1  

#### Output

3

#### Explanation

There are three separate landmass clusters that are not connected to each other.

## Input Format

- First line contains two integers `m` and `n` representing the number of rows and columns  
- The next `m` lines each contain `n` space-separated values (`0` or `1`) representing the grid

## Output Format

- Return a single integer representing the number of distinct landmass clusters

## Constraints

- 1 ≤ m, n ≤ 300  
- Each grid cell is either `0` or `1`

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

breadth-first-search , depth-first-search.

## Company 

snapchat
