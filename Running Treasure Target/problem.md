## Title

Running Treasure Target  


## Slug

running-treasure-target  


## Difficulty

Easy

## Description


You have a trail of treasure spots represented as a sequence of numbers.  
Each number tells you how much treasure (positive) or trap (negative) you collect at that step.  

You are given a `target` value, which represents the amount of treasure you aim to collect.  
Find the `first position (0-based index)` where your `running treasure total` becomes `greater than or equal to` the target.  

If your total never reaches the target, return `-1`.  
 


## Examples

### 1

#### Input

5  
1 2 3 4 5  
8 

#### Output
3

#### Explanation


-Running sums: [1, 3, 6, 10, 15]  
The first index where running sum ≥ 8 is index `3` (sum = 10).  


### 2

#### Input

4  
2 2 2 2  
10 

#### Output

-1

#### Explanation

-Running sums: [2, 4, 6, 8]  
Running sum never reaches 10 → output is -1.  


## Input Format  

- First line: integer `n` — the number of elements in the array.  
- Second line: `n` integers `arr[i]` — the treasure values at each spot.  
- Third line: integer `target` — the desired treasure amount.   

## Output Format  

-Return a single integer — the first index where the running sum ≥ target, or `-1` if not possible.  
  




## Constraints  

- 1 ≤ n ≤ 10000 
- -10⁹ ≤ stars[i] ≤ 10⁹   

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
