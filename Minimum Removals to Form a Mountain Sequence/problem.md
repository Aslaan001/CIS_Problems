## Title  
Minimum Removals to Form a Mountain Sequence  

## Slug  
minimum-removals-to-form-mountain-sequence  

## Difficulty  
Hard  

## Description  

You are given an integer array vals of length n.  
Your task is to make the array a mountain sequence by removing as few elements as possible.  

A mountain sequence must satisfy the following conditions:  
1. Its length is at least 3.  
2. There exists an index i (0 < i < n - 1) such that:  
   - vals[0] < vals[1] < ... < vals[i - 1] < vals[i]  
   - vals[i] > vals[i + 1] > ... > vals[n - 1]  

Return the minimum number of elements to remove from vals so that it becomes a valid mountain sequence.  

If vals is already a mountain sequence, return 0.  

## Examples  

### 1  

#### Input  
3  
1 3 1  

#### Output  
0  

#### Explanation  
The sequence [1, 3, 1] already forms a valid mountain with peak 3.  


### 2  

#### Input  
8  
2 1 1 5 6 2 3 1  

#### Output  
3  

#### Explanation  
Removing indices 0, 1, and 5 gives [1, 5, 6, 3, 1], which is a valid mountain.  


### 3  

#### Input  
7  
1 2 3 4 3 2 1  

#### Output  
0  

#### Explanation  
The sequence is already a valid mountain with peak 4.  


## Input Format  

The first line contains an integer n — the number of elements in the sequence.  
The second line contains n space-separated integers representing the array vals.  


## Output Format  

Return a single integer — the minimum number of elements that must be removed to make the sequence a valid mountain.  


## Constraints  

3 ≤ n ≤ 1000  
1 ≤ vals[i] ≤ 10⁹  


## Time Limit  
1 second  

## Memory Limit  
256 MB  


## Tags  
 
array, dynamic-programming
