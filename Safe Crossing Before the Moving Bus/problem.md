## Title
Safe Crossing Before the Moving Bus

## Slug
safe-crossing-moving-bus

## Difficulty
Hard

## Description
Chris, a small brown bear, wants to cross a straight horizontal road of width w.  
The road is bounded by the parallel lines y = 0 and y = w.

A bus is moving along the road.  
The bus is represented as a convex polygon with n vertices.  
At time 0, the polygon's vertices are given in the plane.  
The bus moves leftward with constant speed v, meaning every x-coordinate of the polygon decreases by v·t as time progresses.

A pedestrian stands at the point (0, 0).  
He can move only vertically along the line x = 0, anywhere between y = 0 and y = w, with any speed not exceeding u.  
He may instantly change speed or direction, but cannot leave the vertical segment.

The pedestrian is considered hit if at any moment he lies strictly inside the polygon (being exactly on its boundary is safe).  
Your task is to determine the minimum time required for the pedestrian to reach (0, w) without ever being hit by the bus.

The answer must be accurate within absolute or relative error 1e−6.

## Examples

### 1
#### Input

5 5 1 2
1 2
3 1
4 3
3 4
1 4

#### Output
5.0000000000


## Input Format
A line containing integers n, w, v, u  
Then n lines, each containing coordinates xi yi of polygon vertices in CCW order

n is the number of polygon vertices  
w is the road width  
v is the bus speed  
u is the pedestrian's maximum vertical speed

## Output Format
Return the minimum time needed to reach (0, w) safely.

## Constraints
3 ≤ n ≤ 10⁴  
1 ≤ w ≤ 10⁹  
1 ≤ v, u ≤ 1000  
−10⁹ ≤ xi ≤ 10⁹  
0 ≤ yi ≤ w  
Polygon is convex and non-degenerate

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
geometry,hackwithinfy.

## Company
infosys
