## Title
Segment Boundary Optimization

## Slug
segment-boundary-optimization

## Difficulty
Hard

## Description
A sequence of unique identifiers from 1 to n is arranged in a specific order, forming a permutation.  
Each position in the sequence has an associated relocation cost.

The sequence must first be divided into two consecutive segments: a left segment and a right segment.  
The split point can be chosen anywhere as long as both segments initially contain at least one element.

After the split, elements may be transferred between the two segments.  
Transferring an element from one segment to the other incurs a cost equal to the relocation cost assigned to that element.

The objective is to transform the two segments so that every value in the left segment is strictly smaller than every value in the right segment.  
If at any moment one of the segments becomes empty, the condition is automatically satisfied.

Your task is to compute the minimum total relocation cost required to achieve this condition.

## Examples

### 1
#### Input
3  
3 1 2  
7 1 4  

#### Output
4  

#### Explanation
By choosing an appropriate initial split and transferring one element across the boundary, the required condition is achieved with a total cost of 4.

### 2
#### Input
4  
2 4 1 3  
5 9 8 3  

#### Output
3  

#### Explanation
A carefully planned split and a minimal set of transfers lead to a total cost of 3. 


## Input Format
- First line contains an integer n, the length of the sequence.
- Second line contains n integers representing a permutation of values from 1 to n.
- Third line contains n integers representing the relocation cost of each element.

## Output Format
- Return a single integer representing the minimum total cost required.

## Constraints
- 2 ≤ n ≤ 2 × 10^5
- Each value from 1 to n appears exactly once
- 1 ≤ relocation cost ≤ 10^9

## Time Limit
2 seconds

## Memory Limit
256 megabytes


## Tags
recursion, hackwithinfy

## Company
infosys
