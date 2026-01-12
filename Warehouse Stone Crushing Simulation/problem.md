## Title  
Warehouse Stone Crushing Simulation  

## Slug  
warehouse-stone-crushing-simulation  

## Difficulty  
Easy  

## Description  

A warehouse stores heavy stones collected from different sites. To optimize storage space, the warehouse uses a crushing machine that repeatedly combines stones based on their weights.

Each stone has a positive integer weight. The crushing machine operates using the following rules:

- As long as there are at least two stones, the machine selects the two heaviest stones.
- Let the weights of these stones be x and y, where x ≤ y.
- If both stones have the same weight, they are completely crushed and removed from the warehouse.
- If the weights are different, the lighter stone is destroyed, and the heavier stone is reduced to a new weight equal to y − x.
- The remaining stone (if any) is placed back into the warehouse.

This process continues until there is at most one stone left in storage.

Your task is to determine the weight of the final remaining stone after all crushing operations are completed.  
If all stones are destroyed, return 0.

## Examples  

### 1  

#### Input  
6  
2 7 4 1 8 1  

#### Output  
1  

### 2  

#### Input  
1  
1  

#### Output  
1  

## Input Format  

- The first line contains an integer n — the number of stones in the warehouse  
- The second line contains n space-separated integers representing the weights of the stones  

## Output Format  

Return a single integer representing the weight of the last remaining stone.  
If no stones remain, return 0.

## Constraints  

1 ≤ n ≤ 30  
1 ≤ stone weight ≤ 1000  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

priority-queue.  
