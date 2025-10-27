## Title  
Remove Nth Node from End  

## Slug  
remove-nth-node-from-end  

## Difficulty  
Easy  

## Description  

You are given the head of a singly linked list and an integer `n`.  
Your task is to remove the `n-th` node from the end of the list and return the head of the updated list.  

If the list has only one node and that node is removed, return an empty list (`null`).  


## Examples  

### 1  

#### Input  
5  
1 2 3 4 5  
2  

#### Output  
1 2 3 5  

#### Explanation  
The 2nd node from the end is `4`.  
After removing it, the new list becomes: `1 → 2 → 3 → 5`.  


### 2  

#### Input  
1  
10  
1  

#### Output  
  

#### Explanation  
The list contains only one node, which is removed, resulting in an empty list.  


## Input Format  
- First line: integer `n` — number of nodes in the linked list.  
- Second line: `n` integers representing the node values.  
- Third line: integer `k` — the position (from the end) of the node to remove.  


## Output Format  
Return the head of the modified linked list after removing the `k-th` node from the end.  
If the list becomes empty, return nothing.  


## Constraints  
- 1 ≤ n ≤ 1000  
- 1 ≤ k ≤ n  
- 0 ≤ node.val ≤ 1000  


## Time Limit  
1 second  

## Memory Limit  
512 MB  


## Tags  
linked-list, two-pointer, deletion
