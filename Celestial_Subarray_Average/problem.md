## Title

Celestial Subarray Average

## Slug

celestial-subarray-average

## Difficulty

Easy

## Description


In the night sky, every star shines with its own unique brightness. These brightness levels are recorded in an array, representing how bright each star appears.

You have been appointed as the Celestial Mathematician, and your task is to identify a group of exactly k consecutive stars whose combined glow appears the brightest on average.

Return this maximum average brightness, accurate up to 10⁻⁵.



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
- Second line: `n` space-separated integers — representing the values in the sacred scroll `Brightness`.  
- Third line: integer `k` — the length of the subarray to consider.

## Output Format  

- Return the `maximum average value` (accurate to 5 decimal places).  



## Constraints  

- 1 ≤ n ≤ 1e4
- 1 ≤ k ≤ n  
- -10⁴ ≤ brightness[i] ≤ 10⁴  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

sliding-window, arrays. 
