## Title
Minimum Steps to Reach Target Position

## Slug
minimum-steps-to-reach-target-position

## Difficulty
Hard

## Description

You control a car on an infinite number line.  
The car starts at position 0 with an initial speed of +1.

The car follows two types of instructions:

- A: accelerate  
  position becomes position + speed  
  speed becomes speed * 2  

- R: reverse direction  
  if speed > 0 then speed becomes -1  
  else speed becomes +1  
  position does not change  

Your task is to determine the minimum number of instructions required so that the car reaches exactly the given target position.

The car may move into negative positions during the process.

## Examples

### 1

#### Input
3

#### Output
2

#### Explanation
A minimal sequence is "A A".  
The car moves: 0 → 1 → 3.

### 2

#### Input
6

#### Output
5

#### Explanation
A valid shortest sequence is "A A A R A".  
The car moves: 0 → 1 → 3 → 7 → 7 → 6.

## Input Format

- A single integer target.

## Output Format

Return a single integer — the minimum number of instructions needed to reach the target.

## Constraints

1 ≤ target ≤ 10000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
breadth-first-search, dynamic-programming, shortest-path

## Company
hackwithinfy
