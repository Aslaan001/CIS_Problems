## Title

Cipher Node Swap


## Slug

cipher-node-swap

## Difficulty

Medium

## Description

In the world of `CipherLand`, there exists a powerful `Cipher Chain` made of nodes, each holding a unique `data value`.  

You, the `Cipher Seeker`, have discovered a special mission:  
Swap the `kth node from the start` with the `kth node from the end` in the Cipher Chain.  

The chain uses `1-based indexing`, and your goal is to return the `updated Cipher Chain` after the swap.



## Examples

### 1 

#### Input

5
1 2 3 4 5
2

#### Output

1 4 3 2 5

#### Explanation

Original chain: `1->2->3->4->5`  
Swap the 2nd node from start (`2`) with 2nd node from end (`4`).  
Updated chain: `1->4->3->2->5`


### 2

#### Input

10
7 9 6 6 7 8 3 0 9 5
5

#### Output

7 9 6 6 8 7 3 0 9 5

#### Explanation

Original chain: `7->9->6->6->7->8->3->0->9->5`  
Swap the 5th node from start (`7`) with 5th node from end (`8`).  
Updated chain: `7->9->6->6->8->7->3->0->9->5`


## Input Format  

- First line: integer `n` — the number of nodes in the Cipher Chain.  
- Second line: `n` integers — the data values of the nodes.  
- Third line: integer `k` — the node position to swap from the start and end (1-based indexing).

-Note:- The Nodes are given in the form of linklist


## Output Format  

Return Head of updated Cipher Chain after performing the swap.



## Constraints  

- 1 ≤ n ≤ 10^5  
- 1 ≤ k ≤ n  
- 0 ≤ node.val ≤ 100    

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

linked-list, arrays.
