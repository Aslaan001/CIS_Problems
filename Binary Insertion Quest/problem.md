## Title

Binary Insertion Quest


## Slug

binary-insertion-quest



## Difficulty

Medium

## Description

You have discovered  sorted array of integers, each holding a magical value.  

Your task is to find the correct `position to insert a given key` into the sorted array so that the array remains sorted.  

Hint:-Use `binary search` to determine the position efficiently.

Return the `0-based index` where the key should be inserted.



## Examples

### 1

#### Input

5 4
1 3 5 6 8

#### Output
2

#### Explanation

The key `4` should be inserted at index `2` to keep the array sorted: `[1, 3, 4, 5, 6, 8]`.
    


### 2

#### Input

4 1
2 4 6 8 

#### Output

0

#### Explanation

The key `1` should be inserted at index `0`: `[1, 2, 4, 6, 8]`.  



## Input Format  

- First line: two integers `n` and `key` — the number of elements in the array and the key to insert.  
- Second line: `n` space-separated integers `arr[i]` — the sorted array.


## Output Format  

- A single integer — the 0-based index where the key should be inserted.
  

## Constraints  

- 1 ≤ n ≤ 10⁵  
- -10⁹ ≤ arr[i], key ≤ 10⁹  
- `arr` is sorted in ascending order and contains distinct elements.  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays , binary-search 
