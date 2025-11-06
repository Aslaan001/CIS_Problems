## Title  
Bitwise OR of Even Numbers  

## Slug  
bitwise-or-of-even-numbers  

## Difficulty  
Easy  

## Description  

You are given an integer array nums.  

Your task is to return the bitwise OR of all even numbers in the array.  

If there are no even numbers, return 0.  

The bitwise OR operation compares each bit of the binary representations of two numbers and sets a bit to 1 if either of the bits is 1.  


## Examples  

### 1  

#### Input  
6  
1 2 3 4 5 6  

#### Output  
6  

#### Explanation  
The even numbers are 2, 4, 6.  
Their bitwise OR equals 6 (2 | 4 | 6 = 6).  


### 2  

#### Input  
3  
7 9 11  

#### Output  
0  

#### Explanation  
There are no even numbers, so the result is 0.  


### 3  

#### Input  
3  
1 8 16  

#### Output  
24  

#### Explanation  
The even numbers are 8 and 16.  
Their bitwise OR equals 24 (8 | 16 = 24).  


## Input Format  

- The first line contains an integer n — the number of elements in the array.  
- The second line contains n space-separated integers representing the array elements nums[i].  


## Output Format  

Return a single integer — the bitwise OR of all even numbers in the array, or 0 if none exist.  


## Constraints  

- 1 ≤ n ≤ 100  
- 1 ≤ nums[i] ≤ 100  


## Time Limit  

1 second  

## Memory Limit  

256 MB  


## Tags  

bitwise-operations, arrays, iteration  
