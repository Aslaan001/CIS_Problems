## Title

Max Books Distribution


## Slug

max-books-distribution



## Difficulty

Medium

## Description

You have a pile of Books that you want to distribute among children as fairly as possible. Your task is to find the `maximum minimum number of Books` each child can get if the candies are divided equally.  

Formally, given an array of integers `Books` where `Books[i]` represents the number of Books in the i-th pile, and an integer `m` representing the number of children, find the largest integer `k` such that it is possible to distribute the Books so that every child receives at least `k` Books.  

Return this maximum possible value of `k`.  



## Examples

### 1

#### Input

5
2 3 5 8 6
3 

#### Output
5

#### Explanation

- Total books = 2 + 3 + 5 + 8 + 6 = 24  
- Distributing among 3 children, each can get at least 5 books.  
    


### 2

#### Input

4
1 2 3 4
2 

#### Output

3

#### Explanation

- Total books = 1 + 2 + 3 + 4 = 10  
- Each child can get at most 3 books.  




## Input Format  

- First line: integer `n` — the number of book piles.  
- Second line: `n` space-separated integers `Books[i]`.  
- Third line: integer `m` — the number of children. 


## Output Format  

- A single integer — the maximum minimum number of books each child can get.  
  

## Constraints  

- 1 ≤ n ≤ 2 × 10⁵  
- 1 ≤ Books[i] ≤ 10⁹  
- 1 ≤ m ≤ 10⁹    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

arrays , binary-search 
