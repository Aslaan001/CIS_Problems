## Title
Square-Removal Stone Game

## Slug
square-removal-stone-game

## Difficulty
Hard

## Description
You are given a pile containing `n` stones. Two players play a turn-based game, with the first player starting.

On each turn, a player must remove a positive number of stones equal to a perfect square (1, 4, 9, 16, ...).  
A player who cannot make a valid move loses the game.

Both players always play optimally.

Your task is to determine whether the first player has a guaranteed winning strategy.

Return `YES` if the first player can force a win, otherwise return `NO`.

## Examples

### 1
#### Input
1

#### Output
true

#### Explanation
The first player removes 1 stone and wins immediately.

### 2
#### Input
2

#### Output
false

#### Explanation
The first player removes 1 stone, leaving 1 for the opponent, who wins.

### 3
#### Input
4

#### Output
true

#### Explanation
The first player removes 4 stones in one move.

## Input Format
- A single integer `n` representing the initial number of stones.

## Output Format
Return `YES` or `NO` depending on whether the first player can guarantee a win.

## Constraints
1 ≤ n ≤ 100000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
game-theory, dynamic-programming, math


## Company
hackwithinfy
