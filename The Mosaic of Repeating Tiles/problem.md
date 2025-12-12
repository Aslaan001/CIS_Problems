## Title
The Mosaic of Repeating Tiles

## Slug
the-mosaic-of-repeating-tiles

## Difficulty
Hard

## Description
In an ancient hall, a long mosaic of colored tiles stretches across the floor.  
The mosaic contains n tiles in a single row, each tile painted with an integer color.

A wandering artist wishes to step across this row, making a sequence of jumps from left to right.  
He is free to begin on any tile and may jump to any later tile.  
The sequence of visited tiles forms a path.

But the artist has a peculiar requirement.  
He considers a path nice if it has the following form:

- The total number of tiles in the path is divisible by k.  
- The tiles can be grouped into consecutive blocks, each block containing exactly k tiles.  
- All tiles in the first block share the same color.  
- All tiles in the second block share the same color.  
- And so on, with each block being monochromatic.

The artist wants to discover the number of possible nice paths that achieve the maximum possible length.  
Since the number may be quite large, compute it modulo 1000000007.

## Examples

### 1
#### Input
5 2  
1 2 3 4 5  

#### Output
1

### 2
#### Input
7 2  
1 3 1 3 3 1 3  

#### Output
4

## Input Format
- First line: integers n and k  
- Second line: n integers representing tile colors c1, c2, ..., cn

## Output Format
Return a single integer — the number of maximum-length nice paths modulo 1000000007.

## Constraints
1 ≤ k ≤ n ≤ 100  
1 ≤ ci ≤ n  

## Time Limit
5 seconds

## Memory Limit
256 megabytes

## Tags
dynamic-programming, hackwithinfy

## Company
infosys
