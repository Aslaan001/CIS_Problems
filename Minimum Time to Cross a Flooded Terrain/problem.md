## Title  
Minimum Time to Cross a Flooded Terrain  

## Slug  
minimum-time-to-cross-flooded-terrain  

## Difficulty  
Hard  

## Description  

A rescue team must cross a square terrain represented as a grid to reach a stranded location.  
Each cell in the grid contains a unique elevation value indicating how high that point is above sea level.

It starts raining, and the water level rises gradually over time.  
At time t, the water level is exactly t, which means:

- Any cell with elevation less than or equal to t is flooded and can be entered.
- Any cell with elevation greater than t is still blocked.

The team starts at the top-left corner of the grid (0, 0) and needs to reach the bottom-right corner (n − 1, n − 1).

The team can move only in four directions: up, down, left, or right.  
They can move instantly between cells as long as both the current cell and the next cell have elevations less than or equal to the current water level.

Your task is to determine the minimum time required for the rescue team to successfully reach the destination.

## Examples  

### 1  

#### Input  
2  
0 2  
1 3  

#### Output  
3  

#### Explanation  

At time 0, only the starting cell is accessible.  
Movement becomes possible only when the water level reaches 3, at which point all required cells are flooded and connected.

### 2  

#### Input  
5  
0 1 2 3 4  
24 23 22 21 5  
12 13 14 15 16  
11 17 18 19 20  
10 9 8 7 6  

#### Output  
16  

#### Explanation  

The team must wait until the water level reaches 16 so that a continuous path exists from the start to the destination.

## Input Format  

- The first line contains an integer n — the size of the grid  
- The next n lines each contain n space-separated integers representing the elevation grid  

## Output Format  

Return a single integer representing the minimum time required to reach the bottom-right cell.

## Constraints  

1 ≤ n ≤ 50  
0 ≤ grid[i][j] < n²  
Each elevation value is unique  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

queue.
