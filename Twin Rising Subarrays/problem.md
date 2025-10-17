## Title

Twin Rising Subarrays


## Slug

twin-rising-subarrays



## Difficulty

Medium

## Description

You have discovered an ancient scroll filled with a sequence of  numbers. Legends say that within this sequence, pairs of rising subarrays hold the key to unlocking hidden energy.  

Your task is to find the `maximum value of 'k'` such that there exist two adjacent strictly increasing subarrays of length `k` each.  

Formally, find the largest `k` for which there exist two subarrays starting at indices `a` and `b` (`a < b`), where:
- Both `nums[a..a + k - 1]` and `nums[b..b + k - 1]` are strictly increasing.
- The subarrays are adjacent, meaning `b = a + k`.

Return this maximum possible value of `k`.  
If no such pair exists, return `0`.



## Examples

### 1

#### Input

10  
2 5 7 8 9 2 3 4 3 1  

#### Output
3

#### Explanation

- The subarray `[7, 8, 9]` (indices 2–4) is strictly increasing.  
- The subarray `[2, 3, 4]` (indices 5–7) is also strictly increasing.  
- They are adjacent, and `k = 3` is the maximum possible value.
    


### 2

#### Input

10  
1 2 3 4 4 4 4 5 6 7  

#### Output

2

#### Explanation

- `[1, 2]` and `[3, 4]` are strictly increasing subarrays of length 2.  
- They are adjacent (`b = a + k`), so `k = 2`.



## Input Format  

- First line: integer `n` — the number of elements in the array.  
- Second line: `n` space-separated integers `arr[i]`.


## Output Format  

- A single integer — the maximum value of `k` satisfying the condition.  
  

## Constraints  

- 2 ≤ n ≤ 2 × 10⁵  
- -10⁹ ≤ arr[i] ≤ 10⁹   

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays , binary-search 
