## Title

Most Frequent Element 

## Slug

most-frequent-element  

## Difficulty

Easy

## Description

You are given an array of integers representing signal readings from distant planets.  
Your task as the `Signal Decoder` is to identify the element that appears `most frequently` in the array.  

If multiple elements have the `same maximum frequency`, return the `smallest` one among them.  

Return this element as a single integer.  


## Examples

### 1

#### Input

7
1 2 2 3 1 4 2

#### Output
2

#### Explanation


- Frequency of 1 → 2  
- Frequency of 2 → 3  
- Frequency of 3 → 1  
- Frequency of 4 → 1  
→ Element with maximum frequency is `2`.

### 2

#### Input

6
5 1 2 2 5 1

#### Output

1

#### Explanation

All elements (1, 2, 5) have frequency 2.  
Hence, the smallest element among them is `1`.

## Input Format  


- First line: integer `n` — the number of elements.  
- Second line: `n` integers `nums[i]` — the elements of the array. 

## Output Format  

- Return a single integer — the element with the maximum frequency (smallest one in case of tie).  




## Constraints  

- 1 ≤ n ≤ 10⁵  
- -10⁹ ≤ nums[i] ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays. 
