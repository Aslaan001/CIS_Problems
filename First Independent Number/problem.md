## Title

First Independent Number


## Slug

first-independent-number  



## Difficulty

Medium

## Description


You are exploring a line of magical stones, each with an integer engraved on it.  

Some stones have numbers that are divisible by earlier stones, making them `dependent`.  
A stone is called `independent` if its number is `not divisible by any previous stone` in the line.  

Your task is to find the `first independent stone` in the array.  

Note:- First Stone Never Be Independent as no stone is  behind it.

Return its `index` (0-based). If all stones are dependent, return `-1`.
 


## Examples

### 1

#### Input

5  
2 4 6 5 8  

#### Output
3

#### Explanation

- Index 1: 4 divisible by 2 → dependent  
- Index 2: 6 divisible by 2 → dependent  
- Index 3: 5 not divisible by 2,4,6 → independent → first independent stone at index 3   


### 2

#### Input

3  
3 6 9    

#### Output

-1

#### Explanation

- Index 1: 6 divisible by 3 → dependent  
- Index 2: 9 divisible by 3 → dependent  
- No independent stone → output -1  


## Input Format  


- First line: integer `n` — number of stones.  
- Second line: `n` integers `arr[i]` — the numbers engraved on the stones.

## Output Format  

- A single integer — the index of the first independent stone, or `-1` if none exist.
  

## Constraints  

- 2 ≤ n ≤ 10⁴  
- -10⁹ ≤ arr[i] ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays . 
