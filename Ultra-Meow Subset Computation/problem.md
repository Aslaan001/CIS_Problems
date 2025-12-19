## Title
Ultra-Meow Subset Computation

## Slug
ultra-meow-subset-computation

## Difficulty
Hard

## Description
A researcher is given a special sequence of numbers consisting of all integers from 1 to n, arranged in an array.  
This sequence is considered perfectly ordered and contains no duplicates.

The researcher is interested in analyzing all possible distinct subsets that can be formed from this array.  
For each such subset b, a special value is computed using a function called MEX.

Let MEX(S, k) be defined as the k-th smallest positive integer (strictly greater than zero) that is not present in the set S.  
Using this definition, MEOW(a) is defined as the sum of MEX(b, |b| + 1) over all distinct subsets b of the array a.

Your task is to compute the value of MEOW(a) efficiently.

Since the number of subsets grows exponentially, the result can be very large.  
Therefore, return the final answer modulo 10^9 + 7.

## Examples

### 1
#### Input
2  

#### Output
12  

#### Explanation
All distinct subsets of the array {1, 2} are considered, and the corresponding MEX values are summed to obtain the final result.

### 2
#### Input
5  

#### Output
184  

#### Explanation
The computation considers all subsets of the array {1, 2, 3, 4, 5} and sums the required MEX values modulo 10^9 + 7.

## Input Format
- Each test case contains a single integer n — the size of the array consisting of integers from 1 to n.

## Output Format
Return a single integer — the value of MEOW(a) modulo 10^9 + 7 for each test case.

## Constraints 
- 1 ≤ n ≤ 5000  
- The sum of n² over all test cases does not exceed 25 × 10^6  

## Time Limit
2.5 seconds

## Memory Limit
256 megabytes

## Tags
maths, hackwithinfy

## Company
infosys
