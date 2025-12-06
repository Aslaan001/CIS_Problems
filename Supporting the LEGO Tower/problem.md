## Title
Supporting the LEGO Tower

## Slug
supporting-lego-tower

## Difficulty
Hard

## Description
Vittorio is building a LEGO Duplo tower using square cuboid bricks.  
Each brick has a 2×2 square base and height 1. All bricks are axis-aligned, have integer coordinates for all corners, and their bases are parallel to the ground.

A brick may sit directly on the ground (z = 0), or it may rest on top of another brick, but only if the two touch in a region of positive area — meaning the lower face of the upper brick must overlap the upper face of the supporting brick.

Vittorio wants to place `purple bricks` at specific required positions.  
The i-th purple brick has the center of its lower base at:

(xᵢ, 0, h)

This means:  
• all purple bricks lie at the same height h  
• all have y = 0  
• their x-coordinates are given in strictly increasing order  
• no two purple bricks overlap

To keep the purple bricks suspended at height h, Vittorio may place `additional (non-purple) bricks`, but only at positions whose lower base centers also satisfy y = 0. Bricks must form a valid connected support tower from ground (z = 0) upward to height h wherever needed.

Your task is to compute the `minimum number of additional bricks` needed so that all required purple bricks are supported and the construction obeys all rules.

It is guaranteed that a valid construction always exists.

## Examples

### 1
#### Input
4 0
2 7 11 13
#### Output
0

#### Explanation

All purple bricks are placed at height h = 0.
A brick at height 0 already rests on the ground, so no extra support is needed.

### 2
#### Input
4 1
2 7 11 13

#### Output
3

#### Explanation

All purple bricks are at height h = 1, so each needs support from a brick at height 0.

Their x-positions (2, 7, 11, 13) are far apart, but we can place support bricks anywhere we choose.
Bricks at x = 2 and x = 7 each need their own support.

However, a single support brick placed at x = 12 has base interval [11,13], which overlaps both purple bricks at x = 11 and x = 13.
So one support brick can hold both of them.

Thus we need supports at: 2, 7, and 12 → total 3 bricks.


## Input Format
A line with integers n and h  
A line with n integers x₁, x₂, …, xₙ in strictly increasing order

n is the number of purple bricks  
h is their common z-coordinate

Each purple brick has center at (xᵢ, 0, h).

## Output Format
Return the minimum number of additional support bricks needed.

## Constraints
1 ≤ n ≤ 300  
0 ≤ h ≤ 10⁹  
1 ≤ xᵢ ≤ 10⁹  
xᵢ < xᵢ₊₁

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
geometry, hackwithinfy.

## Company
infosys
