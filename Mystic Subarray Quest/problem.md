## Title

Mystic Subarray Quest


## Slug

mystic-subarray-quest



## Difficulty

Medium

## Description

You have discovered an ancient sequence of integers. Each number holds a mystical power, but only certain contiguous sequences are stable enough to harness their magic.  

Your task is to find the `length of the longest contiguous subarray` whose `running sum is less than or equal to 'S'`.  

Return the length of this longest subarray.



 


## Examples

### 1

#### Input

5 7
2 1 3 2 1

#### Output
4

#### Explanation

The longest subarray with sum ≤ 7 is `[1,3,2,1]` → sum = 7 → length = 4.
    


### 2

#### Input

6 5
1 2 1 1 1 3 

#### Output

4

#### Explanation

The longest subarray with sum ≤ 5 is `[1,2,1,1]` → sum = 5 → length = 4.  



## Input Format  

- First line: two integers `n` and `S` — the number of elements in the array and the maximum allowed sum.  
- Second line: `n` space-separated integers `arr[i]`.


## Output Format  

- A single integer — the length of the longest contiguous subarray with sum ≤ `S`.
  

## Constraints  

- 1 ≤ n ≤ 10000  
- 1 ≤ arr[i] ≤ 10000     
- 1 ≤ S ≤ 10⁹  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays , runningSum. 
