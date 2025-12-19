## Title
Counting Modular Wall Constructions

## Slug
counting-modular-wall-constructions

## Difficulty
Hard

## Description
A defensive wall must be constructed to protect a settlement from an impending threat.  
The wall is built using rectangular bricks arranged in rows and columns, forming vertical wall segments.

Each wall is defined as a set of brick placements on a grid.  
A wall design specifies exactly which grid positions contain bricks.

You are allowed to build walls using `at least 1 and at most n bricks`.  
The wall has a fixed width C (number of columns), and bricks may be stacked vertically in any column.

Two walls are considered different if there exists at least one position (column, row) where one wall contains a brick and the other does not.

Your task is to compute the total number of distinct wall designs that can be built under these constraints.

Because the number of possible walls can be very large, output the result modulo `10^6 + 3`.

## Examples

### 1
#### Input
5 1  

#### Output
5  

#### Explanation
With width 1, each brick simply stacks vertically, resulting in 5 possible walls.

### 2
#### Input
2 2  

#### Output
5  

#### Explanation
There are 5 distinct ways to place up to 2 bricks across 2 columns.

### 3
#### Input
3 2  

#### Output
9  

#### Explanation
The wall configurations include all arrangements using up to 3 bricks. 

## Input Format
- The input consists of two space-separated integers:
  - n — the maximum number of bricks allowed
  - C — the width of the wall (number of columns)

## Output Format
Return a single integer — the number of different walls that can be constructed, modulo `10^6 + 3`.

## Constraints
- 1 ≤ n ≤ 500000  
- 1 ≤ C ≤ 200000  

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
maths, hackwithinfy

## Company
infosys
