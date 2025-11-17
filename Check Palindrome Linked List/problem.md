## Title  
Check Palindrome Linked List  

## Slug  
check-palindrome-linked-list  

## Difficulty  
Easy  

## Description  

You are given the head of a singly linked list.  
Your task is to determine whether the linked list is a `palindrome` — that is, if the sequence of node values reads the same forward and backward.  

If the linked list is a palindrome, return `true`; otherwise, return `false`.  


## Examples  

### 1  

#### Input  
5  
1 2 3 2 1  

#### Output  
true  

#### Explanation  
The sequence `1 → 2 → 3 → 2 → 1` reads the same both ways, so it is a palindrome.  


### 2  

#### Input  
4  
1 2 2 3  

#### Output  
false  

#### Explanation  
The sequence `1 → 2 → 2 → 3` is not the same backward. Hence, not a palindrome.  


## Input Format  
- First line: integer n — the number of nodes in the linked list.  
- Second line: n integers representing the node values.  

Note: The nodes are provided in order as a linked list.  


## Output Format  
Return `true` if the linked list is a palindrome, otherwise `false`.  


## Constraints  
- 1 ≤ n ≤ 1000  
- 0 ≤ node.val ≤ 1000  


## Time Limit  
1 second  

## Memory Limit  
512 MB  


## Tags  
linked-list  
