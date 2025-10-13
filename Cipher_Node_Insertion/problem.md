## Title

Cipher Node Insertion


## Slug

cipher-node-insertion

## Difficulty

Easy

## Description

In the world of `CipherLand`, special nodes are connected together to form a powerful `Cipher Chain`.  
Each node stores a unique `data value`, and you, the `Cipher Seeker`, have been assigned the task of inserting a new node into this chain at a specific `position`.  

A position of `0` means inserting the node at the `start` of the chain.  
A position of `1` means placing it after the first node, and so on.  

Your mission is to insert the node correctly and return the updated `Cipher Chain`.



## Examples

### 1

#### Input

3  
16 13 7  
1 2

#### Output

16 13 1 7 

#### Explanation

The original Cipher Chain is `16->13->7`.  
After inserting the node `1` at position `2`, the updated Cipher Chain becomes `16->13->1->7`.

### 2

#### Input

4  
5 10 15 20  
25 0  

#### Output

25 5 10 15 20  

#### Explanation

The original Cipher Chain is `5->10->15->20`.  
After inserting the node with value `25` at position `0`, the updated Cipher Chain becomes `25->5->10->15->20`.


## Input Format  

- First line: integer `n` — the number of nodes in the Cipher Chain.  
- Second line: `n` integers representing the data values of each node.  
- Third line: two integers — `data` (value of the new node) and `position` (where to insert it).

-Note:- The Node are given in the form Of LinkList


## Output Format  

Return the updated Cipher Chain after inserting the new node.



## Constraints  

- 1 ≤ n ≤ 1000  
- 0 ≤ node.val ≤ 1000  
- 0 ≤ position ≤ n   

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

linked-list, arrays.