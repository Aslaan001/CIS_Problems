## Title

Relic search


## Slug

relic-search

## Difficulty

Easy

## Description

In the boundless lands of `CipherLand`, there exists a legendary path lined with `Relics of Time`. These relics are arranged in a `Nubeian Order` `(sorted in non-decreasing order)` along a trail that stretches beyond the horizon.  

You, the brave Time Seeker, have been tasked to retrieve a specific relic with a `power value 'k'`. But there’s a catch — the trail is very long, and you `cannot traverse it entirely as you have limited time`. You need a clever strategy to locate the relic efficiently without wandering forever.  

The relics are stored conceptually in an `sorted array 'relics[]'`. Your mission is to find the `index of the target relic`. If the relic is not present, you must return `-1`.

Note:- we are assuming `'0'` based indexing here

---

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
