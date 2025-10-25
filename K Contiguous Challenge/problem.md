## Title

K Contiguous Challenge

## Slug

k-contiguous-challenge

## Difficulty

Medium

## Description

You are tasked with organizing a warehouse represented by an array `arr[]` of item weights. Each weight represents a unique item.  

A new `priority shipment` contains all items whose weight is less than or equal to `k`. To make loading easier, you want `all priority items to be placed together` in a contiguous block.  

You are allowed to swap any two items in the warehouse any number of times.  

Your goal is to `find the minimum number of swaps required` to bring all priority items together, so that they occupy consecutive positions in the array.  



## Examples

### 1

#### Input
5
2 1 5 6 3
3

#### Output
1

#### Explanation
Priority items ≤ 3: `[2,1,3]`.  
Swap index 2 (`5`) with index 4 (`3`) → `[2,1,3,6,5]`.  
Minimum swaps = 1.

### 2

#### Input
7
2 7 9 5 8 7 4
6

#### Output
2

#### Explanation
Priority items ≤ 6: `[2,5,4]`  
Swap index 0 with 2 and index 4 with 6 → `[9,7,2,5,4,7,8]`  
Minimum swaps = 2.

## Input Format
 
- First line: integer `n` — number of items in the warehouse.  
- Second line: `n` integers `arr[i]` — item weights.  
- Third line: integer `k` — maximum weight for priority items.

## Output Format

- For each test case, return a single integer — the minimum number of swaps required to bring all priority items together.



## Constraints

- 1 ≤ n ≤ 10⁶  
- 1 ≤ arr[i] ≤ 10⁶  
- 1 ≤ k ≤ 10⁶  



## Time Limit

1 second

## Memory Limit

512 MB



## Tags

arrays, swaps.