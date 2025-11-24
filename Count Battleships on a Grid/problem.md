## Title

Count Battleships on a Grid

## Slug

count-battleships-on-grid

## Difficulty

Medium

## Description

You are given a 2D grid representing a game board.  
Each cell contains either:

- 'X' — part of a battleship  
- '.' — empty water  

A battleship occupies consecutive cells in a straight line, either horizontally or vertically.  
No two battleships touch each other horizontally or vertically; there is always at least one cell of separation between any two ships.

Your task is to count how many distinct battleships are present on the board.

Each battleship is either:

- 1 × k (horizontal)
- k × 1 (vertical)

## Examples

### 1

#### Input
3 4  
X . . X  
. . . X  
. . . X  

#### Output
2

### 2

#### Input
1 1  
.  

#### Output
0

## Input Format

- First line: two integers m and n  
- Next m lines: n characters ('.' or 'X') representing the board

## Output Format

- Return a single integer: the number of battleships on the board

## Constraints

- 1 ≤ m, n ≤ 200  
- Each cell is either '.' or 'X'

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

grid, counting, scanning, arrays


## Company

Twitch