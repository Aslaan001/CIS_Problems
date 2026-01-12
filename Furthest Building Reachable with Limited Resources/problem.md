## Title  
Furthest Building Reachable with Limited Resources  

## Slug  
furthest-building-you-can-reach  

## Difficulty  
Medium  

## Description  

A city has a straight line of buildings, each with a known height.  
You start at the first building and want to move forward, one building at a time, to reach as far as possible.

To move from building i to building i + 1:

- If the next building is the same height or lower, you can move freely.
- If the next building is taller, you must either:
  - Use bricks equal to the height difference, or
  - Use one ladder, which can cover any height difference.

You are given a limited number of bricks and ladders.  
Both resources can be used in any order, and you should use them optimally.

Your task is to determine the furthest building index (0-based) you can reach.

## Examples  

### 1  

## Input  
7  
4 2 7 6 9 14 12  
5  
1  

## Output  
4  

## Explanation  

- Move from building 0 to 1 freely since 4 ≥ 2  
- Use 5 bricks to move from height 2 to 7  
- Move freely from 7 to 6  
- Use the ladder to move from 6 to 9  
- No resources remain to continue further  

### 2  

## Input  
9  
4 12 2 7 3 18 20 3 19  
10  
2  

## Output  
7  

### 3  

## Input  
4  
14 3 19 3  
17  
0  

## Output  
3  

## Input Format  

- The first line contains an integer n, the number of buildings  
- The second line contains n space-separated integers representing building heights  
- The third line contains an integer bricks  
- The fourth line contains an integer ladders  

## Output Format  

Return a single integer representing the index of the furthest building reachable.

## Constraints  

1 ≤ n ≤ 100000  
1 ≤ heights[i] ≤ 1000000  
0 ≤ bricks ≤ 1000000000  
0 ≤ ladders ≤ n  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

priority-queue  
