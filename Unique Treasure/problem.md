## Title

Unique Treasure


## Slug

unique-treasure 



## Difficulty

Medium

## Description


You are exploring an ancient treasure map represented as an array of integers.  
Each number represents a type of treasure. Some treasures appear multiple times, while others are unique.  

Your task is to find the `index of the first treasure` that appears `exactly once` on the map.  

Return the 0-based index of this treasure. If no unique treasure exists, return `-1`.


 


## Examples

### 1

#### Input

6  
2 3 5 3 2 7   

#### Output
2

#### Explanation

- Treasure types: 2, 3, 5, 3, 2, 7  
- 2 appears twice → not unique  
- 3 appears twice → not unique  
- 5 appears once → first unique treasure at index 2 → output 2    


### 2

#### Input

5  
1 1 2 2 3     

#### Output

4

#### Explanation

- 1 appears twice → not unique  
- 2 appears twice → not unique  
- 3 appears once → first unique treasure at index 4 → output 4 


## Input Format  


- First line: integer `n` — number of treasures on the map.  
- Second line: `n` integers `arr[i]` — treasure types.

## Output Format  

- A single integer — the index of the first unique treasure, or `-1`.
  

## Constraints  

- 1 ≤ n ≤ 10⁴  
- -10⁹ ≤ arr[i] ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
