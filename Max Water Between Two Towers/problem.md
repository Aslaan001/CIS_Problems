## Title

Max Water Between Two Towers

## Slug

max-water-between-two-towers

## Difficulty

Medium

## Description

A row of towers stands along a straight line, each tower having a certain height.  
You want to choose two towers that, together with the ground, can hold the maximum amount of water between them.

The amount of water stored is determined by the distance between the two towers and the height of the shorter tower.  
You cannot tilt or slant the container formed by the two towers.

Given an array of integers representing the heights of the towers, return the `maximum water capacity` achievable.

## Examples

### 1

#### Input

9  
1 8 6 2 5 4 8 3 7

#### Output  
49

#### Explanation

The two towers at indices 1 and 8 can store up to **49 units** of water.

### 2

#### Input

2  
1 1

#### Output  
1

#### Explanation

Both towers have the same height, forming a container of width 1 and height 1.

## Input Format  

- First line: integer `n` — number of towers.  
- Second line: `n` integers `height[i]`.

## Output Format  

- Return a single integer — the maximum amount of water that can be stored.

## Constraints  

- 2 ≤ n ≤ 10⁵  
- 0 ≤ height[i] ≤ 10⁴  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

two-pointers, greedy, arrays

## Company

Google
