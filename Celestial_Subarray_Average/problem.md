## Title

Celestial Subarray Average

## Slug

celestial-subarray-average

## Difficulty

Easy

## Description


In the realm of `Averon`, celestial scholars study patterns hidden within the stars — represented as numbers in the sacred scroll of `Nums`.  

Your task, as the `Celestial Mathematician`, is to discover the `subarray of length 'k' ` that holds the `highest average value`.  

You must compute and return this `maximum average`, accurate up to `10⁻⁵`.  

If multiple subarrays yield the same average, any of them is acceptable — the heavens shall honor your precision.



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
