## Title

Celestial Subarray Average

## Slug

celestial-subarray-average

## Difficulty

Easy

## Description


In the Sky of `Arexona`, numbers in the `Nums` represent the brightness of stars.  
Your task, as the `Celestial Mathematician`, is to find the `subarray of length k` that has the `highest average brightness``.

Return this `maximum average value`, accurate up to `10⁻⁵`.

If there are multiple subarrays with the same average, returning any one of them is perfectly fine.



## Examples

### 1

#### Input

6
1 12 -5 -6 50 3
4

#### Output

12.75000

#### Explanation

The subarray `[12, -5, -6, 50]` has the highest average:  
\[
(12 - 5 - 6 + 50) / 4 = 12.75
\]

### 2

#### Input

1
5
1

#### Output

5.00000

#### Explanation

Only one element exists, so the average is `5.00000`.  

## Input Format  


- First line: integer `n` — the number of celestial numbers.  
- Second line: `n` space-separated integers — representing the values in the sacred scroll `Nums`.  
- Third line: integer `k` — the length of the subarray to consider.

## Output Format  

- Return the `maximum average value` (accurate to 5 decimal places).  



## Constraints  

- 1 ≤ n ≤ 1e4
- 1 ≤ k ≤ n  
- -10⁴ ≤ nums[i] ≤ 10⁴  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

sliding-window, arrays. 
