## Title  
Hazard Trail Survival

## Slug  
hazard-trail-survival

## Difficulty  
Medium

## Description  

You are given an m x n grid of integers representing a hazardous trail.

The traveler starts at cell (0, 0) and must reach cell (m - 1, n - 1).  
Movement is allowed only to the right or downward.

Each cell affects the traveler's stamina:
- A negative value decreases stamina
- A positive value increases stamina
- Zero leaves stamina unchanged

The traveler's stamina must always remain strictly greater than zero at every step.  
If stamina ever becomes zero or negative, the traveler cannot continue.

Your task is to determine the minimum initial stamina required so that the traveler can safely reach the destination.

## Examples  

### 1  

#### Input  
3 3  
-2 -3 3  
-5 -10 1  
10 30 -5

#### Output  
7

#### Explanation  
If the traveler starts with 7 stamina and follows a safe path, stamina never drops to zero or below.

### 2  

#### Input  
1 1  
0

#### Output  
1

#### Explanation  
Even without hazards, the traveler must begin with at least 1 stamina.

## Input Format  

- The first line contains two integers m and n.  
- Each of the next m lines contains n integers representing the grid.

## Output Format  

Return a single integer: the minimum initial stamina required.

## Constraints  

1 ≤ m, n ≤ 200  
-1000 ≤ grid[i][j] ≤ 1000  

## Time Limit  
1 second  

## Memory Limit  
512 MB  

## Tags  
dynamic programming, grid traversal
