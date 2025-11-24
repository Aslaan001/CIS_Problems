## Title  
Count Valid Military Trios  

## Slug  
count-valid-military-trios  

## Difficulty  
Medium  

## Description  

There are `n` soldiers standing in a straight line, each assigned a unique rank value.  

You need to count the number of valid military trios (teams of 3 soldiers) that can be formed under the following conditions:  

The soldiers must be chosen in order of their positions `(i, j, k)` such that `0 ≤ i < j < k < n`.  
A trio is considered valid if one of these is true:  
1. `rank[i] < rank[j] < rank[k]` (strictly increasing order)  
2. `rank[i] > rank[j] > rank[k]` (strictly decreasing order)  

Return the total number of valid trios possible.  

Each soldier can be part of multiple trios.  

## Examples  

### 1  

#### Input  
5  
2 5 3 4 1  

#### Output  
3  

#### Explanation  
The valid trios are:  
(2, 3, 4)  
(5, 4, 1)  
(5, 3, 1)  


### 2  

#### Input  
3  
2 1 3  

#### Output  
0  

#### Explanation  
No valid increasing or decreasing trio can be formed.  


### 3  

#### Input  
4  
1 2 3 4  

#### Output  
4  

#### Explanation  
The valid trios are all increasing:  
(1, 2, 3), (1, 2, 4), (1, 3, 4), (2, 3, 4).  

## Input Format  

The first line contains an integer `n` — the number of soldiers.  
The second line contains `n` space-separated integers representing the soldiers' ranks.  

## Output Format  

Return a single integer — the total number of valid trios that can be formed.  

## Constraints  

3 ≤ n ≤ 1000  
1 ≤ rank[i] ≤ 100000  
All ranks are unique.  

## Time Limit  
1 second  

## Memory Limit  
256 MB  

## Tags  
array, dynamic-programming
