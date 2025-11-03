## Title

Running Treasure Target  


## Slug

running-treasure-target  


## Difficulty

Easy

## Description


You have a trail of treasure spots represented as a sequence of numbers in the form of an array

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


#### Explanation  
- Running sums step by step: `[1, 3, 6, 10, 15]`  
- At index `0`: sum = 1 (still less than 8)  
- At index `1`: sum = 3  
- At index `2`: sum = 6  
- At index `3`: sum = 10 (first time ≥ 8)  

Hence, the first index where running sum ≥ target is `3`.  
Even though the final total is much higher (15),  
we only care about the first point where we reach or cross the target.  


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
- -10⁹ ≤ arr[i] ≤ 10⁹ 
- -10⁹ ≤ target ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
