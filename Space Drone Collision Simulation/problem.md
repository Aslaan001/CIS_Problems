## Title

Space Drone Collision Simulation

## Slug

space-drone-collision

## Difficulty

Medium

## Description

You are given an array `drones` of integers representing autonomous drones traveling through a narrow space tunnel.  
Each drone has:

- A `size` represented by its absolute value  
- A `direction` represented by its sign  
  - Positive → moving forward  
  - Negative → moving backward  

All drones move at the same speed.

When two drones moving toward each other meet:

- The `smaller drone is destroyed`
- If both have the same size, `both are destroyed`
- Drones moving in the same direction never collide

Return the final configuration of drones after all collisions have resolved.

## Examples

### 1

#### Input

drones = [5, 10, -5]

#### Output

[5, 10]

### 2

#### Input

drones = [8, -8]

#### Output

[]

### 3

#### Input

drones = [10, 2, -5]

#### Output

[10]

### 4

#### Input

drones = [3, 5, -6, 2, -1, 4]

#### Output

[-6, 2, 4]

## Input Format

- A single line containing an integer array `drones`.

## Output Format

- Return the final state of the drone array after all collisions.

## Constraints

- 2 ≤ drones.length ≤ 10⁴  
- -1000 ≤ drones[i] ≤ 1000  
- drones[i] ≠ 0  

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

stack
