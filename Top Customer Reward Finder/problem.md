## Title  
Top Customer Reward Finder  

## Slug  
top-customer-reward-finder  

## Difficulty  
Medium  

## Description  

An e-commerce company keeps a record of all customer spending amounts in an integer array `nums`,  
where each value represents how much a customer has spent in a single transaction.  

At the end of the month, the company wants to identify its `top spenders` for reward distribution.  
To do this, management needs to find the `k-th highest spending amount` among all customers.  

Your task is to determine and return the spending amount that ranks exactly `k-th`  
when the array is sorted in `descending order`.  


## Examples  

### 1  

#### Input  
6  
3 2 1 5 6 4  
2  

#### Output  
5  

#### Explanation  
Sorted in descending order → `6 5 4 3 2 1`  
The 2nd highest spending amount is `5`.  


### 2  

#### Input  
5  
7 10 4 3 20  
4  

#### Output  
7  

#### Explanation  
Sorted in descending order → `20 10 7 4 3`  
The 4th highest spending amount is `7`.  


### 3  

#### Input  
8  
9 9 8 3 2 4 8 5  
3  

#### Output  
8  

#### Explanation  
Sorted in descending order → `9 9 8 8 5 4 3 2`  
The 3rd highest amount is `8`.  

## Input Format  

- First line contains an integer `n` — the number of transactions.  
- Second line contains `n` space-separated integers representing the spending amounts.  
Third line contains an integer `k`.  

## Output Format  

Return the `k-th highest spending amount`.  

## Constraints  

1 ≤ n ≤ 10⁴  
−10⁴ ≤ nums[i] ≤ 10⁴ 
1 ≤ k ≤ n 

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

array, sorting
