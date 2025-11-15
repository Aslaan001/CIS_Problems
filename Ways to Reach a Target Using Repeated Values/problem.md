## Title  
Ways to Reach a Target Using Repeated Values  

## Slug  
ways-to-reach-target-repeated-values  

## Difficulty  
Medium  

## Description  

You are given an integer `target` and an array `vals` containing distinct positive integers.  
You may use each value from `vals` any number of times.

Your task is to determine how many different combinations of these values can sum exactly to `target`.  
The order of selection does not matter — only the counts of each value determine uniqueness.

If it is not possible to form the target, output `0`.  


## Examples  

### 1  

#### Input  
5  
3  
1 2 5  

#### Output  
4  

#### Explanation  
Valid combinations include:  
5  
2 2 1  
2 1 1 1  
1 1 1 1 1  


### 2  

#### Input  
3  
1  
2  

#### Output  
0  

#### Explanation  
Value `2` cannot produce `3` no matter how many times it is used.  


### 3  

#### Input  
10  
1  
10  

#### Output  
1  

#### Explanation  
Only one combination is possible: `10`.  


## Input Format  

- The first line contains an integer `target`.  
- The second line contains an integer `n` — the count of available values.  
- The third line contains `n` space-separated integers representing `vals[i]`.  


## Output Format  

Return a single integer — the number of distinct combinations to form the target.  


## Constraints  

- 1 ≤ n ≤ 300  
- 1 ≤ vals[i] ≤ 5000  
- 0 ≤ target ≤ 5000  
- All values in `vals` are distinct.  


## Time Limit  

1 second  

## Memory Limit  

256 MB  


## Tags  

dynamic-programming.
