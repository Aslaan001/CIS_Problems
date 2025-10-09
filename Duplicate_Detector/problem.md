## Title

Duplicate Detector


## Slug

duplicate-detector

## Difficulty

Easy

## Description

In the world of `HinderLand`, every array of numbers hides a secret pattern.  

You, the `Cipher Seeker`, are given an array of integers — known as the `Cipher Sequence`.  
Your mission: determine if `any number appears at least twice` in the sequence `within a distance of 'k' positions` from each other.  

If such a pair exists, return `true`; otherwise, return `false`.

## Examples

### 1

#### Input

4
1 2 3 1
3

#### Output

true

#### Explanation

The number `1` appears twice, and the distance between the two `1`s is `3 - 0 = 3`, which is ≤ `k (3)`.  
Hence, return `true`.

### 2

#### Input

6
1 2 3 1 2 3
2

#### Output

false

#### Explanation

No duplicate numbers appear within a distance of `2`.  
All repeated numbers are farther apart.

## Input Format  

- First line: integer `n` — the size of the Cipher Sequence.  
- Second line: `n` space-separated integers — elements of the Cipher Sequence.  
- Third line: integer `k` — the maximum allowed distance between two duplicate numbers.

## Output Format  

Return `true` if there exist two identical numbers within distance `k`, otherwise print `false`.  



## Constraints  

- 1 ≤ n ≤ 1e4  
- −1e9 ≤ nums[i] ≤ 1e9  
- 0 ≤ k ≤ 1e5  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays, sliding-window. 
