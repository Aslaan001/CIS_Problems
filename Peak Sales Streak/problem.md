## Title  
Peak Sales Streak  

## Slug  
peak-sales-streak  

## Difficulty  
Medium  

## Description  

A retail analytics company tracks daily profit changes of a store in an integer array `nums`,  
where each element represents the `net profit or loss` for that day.  

Management wants to find the `most profitable continuous streak of days`,  
that is, the consecutive period where the total sum of profits is the highest.  
You need to identify and return the total profit of this best-performing streak.  

## Examples  

### 1  

#### Input  
11  
3 -2 5 -1 4 -3 2 3 -2 4 -1  

#### Output  
13 

#### Explanation  
The best profitable streak is `[3, -2, 5, -1, 4, -3, 2, 3, -2, 4]`,  
which gives a total profit of `13`.

### 2  

#### Input  
6  
-5 -2 4 -1 2 3  

#### Output  
8  

#### Explanation  
The streak `[4, -1, 2, 3]` gives the maximum profit sum `8`.  

### 3  

#### Input  
5  
-2 -3 -1 -4 -6  

#### Output  
-1  

#### Explanation  
All days show losses, so the least loss day `-1` is the maximum possible total.  

## Input Format  

- First line contains an integer `n` — the number of days.  
- Second line contains `n` space-separated integers representing the profit or loss for each day.  

## Output Format  

Return the `maximum total profit` possible in a continuous streak of days.  

## Constraints  

1 ≤ n ≤ 10⁵  
−10⁴ ≤ nums[i] ≤ 10⁴  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

array
