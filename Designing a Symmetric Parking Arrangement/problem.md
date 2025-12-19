## Title
Designing a Symmetric Parking Arrangement

## Slug
designing-a-symmetric-parking-arrangement

## Difficulty
Hard

## Description
An IT company provides cars to all of its employees, choosing from exactly four different car brands.  
The parking lot in front of the office consists of a single straight line of parking spaces.

The total number of parking spaces is fixed at (2n − 2).  
There are always more cars available than parking spaces, and there are no empty spots at any time.

The company’s CEO wants the parking lot to look visually appealing.  
To achieve this, the CEO requires that the parking lot contains `exactly n consecutive cars of the same brand` somewhere in the line.

All cars are parked in a single row, and each parking space must be occupied by exactly one car of one of the four brands.

Your task is to calculate how many different ways the parking lot can be filled while satisfying the condition above.

Two arrangements are considered different if there exists at least one parking position where the car brands differ.

## Examples

### 1
#### Input
3  

#### Output
24  

#### Explanation
For n = 3, the parking lot has 4 parking spaces.  
Each valid arrangement contains exactly 3 consecutive cars of the same brand.

## Input Format
- The input contains a single integer n — the required number of consecutive cars of the same brand.

## Output Format
Return a single integer — the number of valid ways to fill the parking lot.

## Constraints
- 3 ≤ n ≤ 30  

## Time Limit
0.5 seconds

## Memory Limit
64 megabytes


## Tags
maths, hackwithinfy

## Company
infosys
