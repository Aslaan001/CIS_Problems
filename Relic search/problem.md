## Title

Relic search


## Slug

relic-search

## Difficulty

Easy

## Description

In the vast lands of `CipherLand`, relics with mysterious power values are arranged along a long trail in `non-decreasing order`, in the form of an array called relics.  

You, the `Time Seeker`, are looking for a relic with a specific power value `k`.  

If the relic exists, return its `index`.  
If it doesn’t, return `-1`.  

`Note: Use '0' based indexing`.


## Examples

### 1

#### Input

4
3 6 7 11
6

#### Output

1

#### Explanation

The relic with power 6 is located at index 1.

### 2

#### Input

11
3 5 7 9 10 90 100 130 140 160 170
4

#### Output

-1

#### Explanation

The relic with power 4 is not located at any index so -1.


## Input Format  


- First line: a conceptual infinite sorted array `relics[]` of integers.  
- Second line: integer `k` — the power value of the target relic.

## Output Format  

Return a single integer — the `index of the target relic` in the array. If not found, return `-1`.



## Constraints  

- 1 ≤ n ≤ 1e4    
- 1 ≤ arr[i] ≤ 1e9  
- 0 ≤ k ≤ 1e9 

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

binary-search, arrays. 
