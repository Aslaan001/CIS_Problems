## Title

First Peak Index


## Slug

first-peak-index 


## Difficulty

Medium

## Description


You are hiking along a trail represented as a sequence of elevations.  
Each integer in the array represents the height of the terrain at that step.  

Your goal is to find the `first peak index` — the smallest index `i` such that:  

- The sum of elevations before `i` is less than the elevation at `i`.  
- The sum of elevations after `i` is also less than the elevation at `i`.  

If no such peak exists, return `-1`.
 


## Examples

### 1

#### Input

4
1 5 2 1 

#### Output
1


#### Explanation
At index `1`:  
- Sum of elements before = 1 < 5  
- Sum of elements after = 2 + 1 = 3 < 5  
→ Both conditions satisfied → output `1`.  



### 2

#### Input

5
1 3 2 4 1

#### Output

-1

#### Explanation

No index satisfies the peak condition — output `-1`.


## Input Format  

- First line: integer `n` — number of elevations.  
- Second line: `n` integers `arr[i]` — elevation values along the trail.

## Output Format  

- A single integer — the first index that is a peak according to the conditions, or `-1` if none exist.
  




## Constraints  

- 1 ≤ n ≤ 10⁴  
- 0 ≤ arr[i] ≤ 10⁹     

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
