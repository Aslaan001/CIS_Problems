## Title
Navigating an Infinite Grid with Adjustable Steps

## Slug
navigating-an-infinite-grid-with-adjustable-steps

## Difficulty
Medium

## Description
A robot is placed at the origin cell (0, 0) of an infinite two-dimensional grid.  
The robot is equipped with adjustable-length legs that determine how far it can move in a single jump.

Initially, the length of the robot’s legs is set to 1.

At any moment, if the robot is located at cell (x, y) and its leg length is m, it may perform exactly one of the following actions in a single move:
- Jump to the cell (x + m, y)
- Jump to the cell (x, y + m)
- Increase the leg length by 1, changing m to m + 1

The robot’s goal is to reach a target cell (a, b) starting from (0, 0).

Your task is to determine the minimum number of moves required for the robot to reach the target cell.

## Examples

### 1
#### Input
1 1  

#### Output
2  

#### Explanation
The robot can jump to (0, 1) and then to (1, 1).  
Increasing the leg length would cause the robot to overshoot the target.

### 2
#### Input
1 6  

#### Output
5  

#### Explanation
The robot first jumps to (1, 0), increases its leg length, and then makes successive jumps to reach the destination.

### 3
#### Input
8 4  

#### Output
6  

#### Explanation
The robot increases its leg length to 4, jumps to (0, 4), and then makes two jumps to reach (8, 4).

## Input Format
- Each test case consists of a single line containing two integers a and b — the coordinates of the target cell.

## Output Format
Return a single integer — the minimum number of moves required to reach the target cell.

## Constraints  
- 1 ≤ a, b ≤ 10^9  

## Time Limit
2 seconds

## Memory Limit
256 megabytes


## Tags
maths, hackwithinfy

## Company
infosys
