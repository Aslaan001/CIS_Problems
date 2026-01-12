## Title  
Minimum Pair Merges to Stabilize Inventory Order  

## Slug  
minimum-pair-removal-to-sort-array  

## Difficulty  
Easy  

## Description  

A warehouse maintains a sequence of inventory adjustment values recorded over time.  
Due to system constraints, the sequence must eventually become `non-decreasing` so that each adjustment is not smaller than the previous one.

To achieve this, the system allows a special merge operation that can be performed any number of times:

- Select the `adjacent pair with the minimum sum` in the array.
- If multiple adjacent pairs have the same minimum sum, select the `leftmost` such pair.
- Replace this pair with a single value equal to their sum.

Each merge counts as one operation.

Your task is to determine the `minimum number of operations` required to transform the array into a non-decreasing sequence.

An array is considered non-decreasing if every element is greater than or equal to the one before it.

## Examples  

### 1  

#### Input  
4  
5 2 3 1  

#### Output  
2  

#### Explanation  

- The adjacent pair (3, 1) has the minimum sum of 4 → array becomes [5, 2, 4]  
- The adjacent pair (2, 4) has the minimum sum of 6 → array becomes [5, 6]  
- The array is now non-decreasing after 2 operations  

### 2  

#### Input  
3  
1 2 2  

#### Output  
0  

#### Explanation  

The array is already non-decreasing, so no operations are needed.

## Input Format  

- The first line contains an integer n — the length of the array  
- The second line contains n space-separated integers representing the array values  

## Output Format  

Return a single integer representing the minimum number of merge operations required.

## Constraints  

1 ≤ n ≤ 50  
-1000 ≤ nums[i] ≤ 1000  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

queue.
