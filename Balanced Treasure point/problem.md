## Title

Balanced Treasure Point


## Slug

balanced-treasure-point  


## Difficulty

Easy

## Description


You are walking along a line of treasure spots, each represented by an integer value.  
Positive numbers mean treasure gained, negative numbers mean traps that reduce your total.  

Your task is to find the `smallest index` where the sum of all treasures to the left equals the sum of all treasures to the right.  

If no such index exists, return `-1`. 
 


## Examples

### 1

#### Input

5
1 7 3 6 5 6 

#### Output
3

#### Explanation
Total sum = 28  
At index 3:  
Left sum = 1 + 7 + 3 = 11  
Right sum = 28 - 11 - 6 = 11  
→ Both sides equal → output `3`. 


### 2

#### Input

4  
2 2 2 2 

#### Output

-1

#### Explanation

-No index balances left and right sums.  


## Input Format  

- First line: integer `n` — number of treasure spots.  
- Second line: `n` integers `arr[i]` — the treasure values at each spot.

## Output Format  

- A single integer — the smallest index where left sum equals right sum, or `-1` if no such index exists.
  




## Constraints  

- 1 ≤ n ≤ 10⁴  
- -10⁹ ≤ arr[i] ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
