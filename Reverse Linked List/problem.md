## Title  
Reverse Linked List  

## Slug  
reverse-linked-list  

## Difficulty  
Easy  

## Description  

In the problem, each chain of nodes flows in one direction.  
Your mission is to `reverse the direction` of this chain, so the last node becomes the first.  

You are given the head of a linked list.  
Return the new head of the list after reversing it.  


## Examples  

### 1  

#### Input  
5  
10 20 30 40 50  

#### Output  
50 40 30 20 10  

#### Explanation  
After reversing, the order of nodes becomes opposite.  
Hence, the new list is `50 → 40 → 30 → 20 → 10`.  


### 2  

#### Input  
4  
5 10 15 20  

#### Output  
20 15 10 5  

#### Explanation  
Original chain: 5 → 10 → 15 → 20  
Reversed chain: 20 → 15 → 10 → 5  


## Input Format  
- First line: integer n — the number of nodes in the linked list.  
- Second line: n integers representing the data values of each node.  

Note: The nodes are provided as a linked list in order.  


## Output Format  
Return the new head of the reversed linked list, printed from head to tail.  


## Constraints  
- 1 ≤ n ≤ 1000  
- 0 ≤ node.val ≤ 1000  


## Time Limit  
1 second  

## Memory Limit  
512 MB  


## Tags  
linked-list, reverse, basic
