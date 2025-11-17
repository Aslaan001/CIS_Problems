## Title

Find MEX of Array


## Slug

find-mex-of-array 


## Difficulty

Easy

## Description


You are given an array of non-negative integers.  

Your task is to find the `MEX (Minimum Excludant)` of the array — the smallest non-negative integer that does `not` appear in the array.  

Return this integer as the result.
 


## Examples

### 1

#### Input

5  
0 1 2 4 5 

#### Output
3

#### Explanation
The array contains 0, 1, 2, 4, 5.  
The smallest non-negative integer missing is `3`.


### 2

#### Input

4  
1 2 3 0  

#### Output

4

#### Explanation

The array contains 0, 1, 2, 3.  
The smallest missing non-negative integer is `4`.


## Input Format  

- First line: integer `n` — number of elements in the array.  
- Second line: `n` integers `arr[i]` — elements of the array.

## Output Format  

- A single integer — the MEX of the array.
  

## Constraints  

- 1 ≤ n ≤ 10⁴  
- -10⁹ ≤ arr[i] ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

array 
