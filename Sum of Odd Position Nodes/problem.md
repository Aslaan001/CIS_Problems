## Title

Sum of Odd Position Nodes

## Slug

sum-of-odd-position-nodes

## Difficulty

Easy

## Description

In the Kingdom, every chain of nodes holds special values.  
Your mission as a King of Kingdom is to calculate the total sum of all nodes that appear at `odd positions` in the chain.  

Positions are `1-based`, meaning the first node is at position `1`, the second at `2`, and so on.  

Return the total sum of all node values located at odd positions.


## Examples

### 1

#### Input

5  
10 20 30 40 50  

#### Output

90  

#### Explanation

Nodes at odd positions are `10`, `30`, and `50`.  
Sum = 10 + 30 + 50 = 90.

---

### 2

#### Input

4  
5 15 25 35  

#### Output

30  

#### Explanation

Nodes at odd positions are `5` and `25`.  
Sum = 5 + 25 = 30.


## Input Format

- First line: integer `n` — the number of nodes in the Cipher Chain.  
- Second line: `n` integers representing the data values of each node.

-Note:- The Node are given in the form Of LinkList  


## Output Format

Return the sum of node values at odd positions in the  Chain.


## Constraints

- 1 ≤ n ≤ 1000  
- 0 ≤ node.val ≤ 1000  

---

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

linked-list, sum, basic
