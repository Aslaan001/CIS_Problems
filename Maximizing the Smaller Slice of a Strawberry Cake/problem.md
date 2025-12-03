## Title
Maximizing the Smaller Slice of a Strawberry Cake

## Slug
maximize-smaller-cake-slice

## Difficulty
Hard

## Description
Anon is celebrating a birthday, and Soyo buys a perfectly round strawberry cake to share.  
The cake is represented as a circle of radius r, centered at the origin (0, 0).

There are n strawberries placed on the cake.  
The i-th strawberry is located at (xi, yi), and each satisfies:

Their distance from the center is at most 0.9·r, meaning all strawberries lie strictly inside the cake.  
No two strawberries share the same coordinates.

Soyo wants to cut the cake using a single straight line.  
Anon must receive all strawberries, and if a strawberry lies exactly on the line, Soyo may assign it to either piece.

Among all valid cuts, Soyo wants the smaller resulting piece to be as large as possible.  
Your task is to compute the maximum possible area of this smaller piece.

Answers are accepted within absolute or relative error 1e−6.

## Examples

### Example 1
#### Input

4 5
-3 -3
3 -3
-3 3
3 3
#### Output
11.182380450040

### 2
#### Input
7 15
9 -4
2 -2
8 3
0 4
-6 10
6 6
3 5

#### Output
353.429173528852



## Input Format
A line containing two integers n and r  
n is the number of strawberries  
r is the radius of the cake

The next n lines each contain two integers xi, yi representing strawberry coordinates.

## Output Format
Return a single real number: the maximum possible area of the smaller piece of cake when the cut ensures all strawberries lie on the same side of the line.

## Constraints
1 ≤ n ≤ 2 × 10⁵  
1 ≤ r ≤ 10⁶  
sqrt(xi² + yi²) ≤ 0.9r  
All strawberry positions are distinct

## Time Limit
1 second

## Memory Limit
256 megabytes

## Tags
geometry, circle, half-plane, angular-sweep, optimization, trigonometry
