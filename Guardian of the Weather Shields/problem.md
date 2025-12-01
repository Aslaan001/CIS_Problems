## Title
Guardian of the Weather Shields

## Slug
weather-shields-guardian-hard

## Difficulty
Hard

## Description
A futuristic region contains n outposts arranged along a straight line, numbered from 1 to n.

For the next m days, meteorological scanners predict energy storms.  
On day i, a storm beam will strike the outposts in the interval [li, ri].  
An outpost is considered safe if it is never struck by any beam during the m days.

You operate an ancient shield controller capable of neutralizing storms.  
You may choose k days, and on these selected days all storm activity is completely cancelled.  
Your objective is to determine the maximum number of safe outposts that can remain after selecting which k storm days to neutralize.

## Examples

### 1
#### Input
2 3 2  
1 2  
1 2  
1 1
#### Output
1

### 2
#### Input
5 3 2  
1 3  
2 4  
3 5
#### Output
2

### 3
#### Input
10 6 4  
1 5  
6 10  
2 2  
3 7  
5 8  
1 4
#### Output
6

## Input Format    
A line with integers n, m and k.  
Then m lines follow, each containing li and ri.

## Output Format
Return one integer representing the maximum number of safe outposts.

## Constraints 
1 ≤ n ≤ 200000  
2 ≤ m ≤ 200000  
2 ≤ k ≤ min(10, m)  
1 ≤ li ≤ ri ≤ n  
The total sum of all n values does not exceed 200000.  
The total sum of all m values does not exceed 200000.

## Time Limit
4000

## Memory Limit
1024

## Tags
greedy, intervals, bruteforce, two-pointers, combinatorics
