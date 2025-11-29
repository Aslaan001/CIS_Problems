## Title
Count Valid Pickup-Delivery Sequences

## Slug
count-valid-pickup-delivery-sequences

## Difficulty
Hard

## Description

You are given an integer n representing the number of service requests.  
Each request consists of two events:

1. A pickup event  
2. A delivery event  

For every request i, the delivery event must appear `after` its corresponding pickup event in the sequence.

Your task is to determine the number of different valid sequences that contain all pickup and delivery events for the n requests, while respecting the rule above.

Since the total number of valid sequences can be large, return the result modulo 1000000007.

## Examples

### 1

#### Input
1

#### Output
1

#### Explanation
There is only one valid sequence: P1, D1.

### 2

#### Input
2

#### Output
6

#### Explanation
There are six valid sequences that respect the rule that each delivery must come after its pickup.

### 3

#### Input
3

#### Output
90

## Input Format

- The first line contains an integer n.

## Output Format

Return a single integer — the number of valid pickup-delivery sequences modulo 1000000007.

## Constraints

1 ≤ n ≤ 500

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
combinatorics, math, counting, dynamic-programming


## Company
hackwithinfy
