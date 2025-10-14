## Title

Merge Loot


## Slug

merge-loot

## Difficulty


## Description

You are a master thief planning the ultimate heist. You have two loot collections from different banks, represented as two integer arrays `nums1` and `nums2`, sorted in non-decreasing order. Each number represents the value of an artifact in the loot.  

Your task is to merge all loot into a single bag, arranged in non-decreasing order of value, so it’s easier to manage.




## Examples

### 1

#### Input

3
1 2 3
3
2 5 6

#### Output

1 2 2 3 5 6

#### Explanation

The loots from two banks are [1,2,3] and [2,5,6].
After merging them into a single bag in sorted order, you get [1,2,2,3,5,6]

### 2

#### Input

1
1
0

#### Output

1

#### Explanation

The first bank has loot [1], and the second bank has no loot.
Merged loot remains [1].


## Input Format  


- First line: integer `n` — number of artifacts in the first bank (`nums1`)  
- Second line: `n` integers — values of the first bank loot, in non-decreasing order  
- Third line: integer `m` — number of artifacts in the second bank (`nums2`)  
- Fourth line: `m` integers — values of the second bank loot, in non-decreasing order  


## Output Format  

Return the merged loot array `nums1` with all values in non-decreasing order.



## Constraints  

- 1 ≤ n ≤ 100
- 1 ≤ nums1[i] ≤ 1e9 
- 1 ≤ m ≤ 100
- 1 ≤ nums2[i] ≤ 1e9  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays. 
