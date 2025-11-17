## Title  
Find Middle Element  

## Slug  
find-middle-element  

## Difficulty  
Easy  

## Description  

In the Kingdom, each chain of nodes represents a line of wisdom.  
Your task is to find the `middle node` in this chain.  

If the number of nodes is `odd`, return the data of the middle node.  
If the number of nodes is `even`, return the `second middle node` (the one appearing later in the chain).  


## Examples  

### 1  

#### Input  
5  
10 20 30 40 50  

#### Output  
30  

#### Explanation  
There are 5 nodes.  
The middle node is at position 3 (value = 30).  
Hence, the output is 30.  


### 2  

#### Input  
4  
5 10 15 20  

#### Output  
15  

#### Explanation  
There are 4 nodes (even count).  
Middle nodes are positions 2 and 3 — values 10 and 15.  
We return the second middle node, which is 15.  


## Input Format  
- First line: integer n — the number of nodes in the linked list.  
- Second line: n integers representing the data values of each node.  

Note: The nodes are provided as a linked list in order.  


## Output Format  
Return the data value of the middle node.  


## Constraints  
- 1 ≤ n ≤ 1000  
- 0 ≤ node.val ≤ 1000  


## Time Limit  
1 second  

## Memory Limit  
512 MB  


## Tags  
linked-list
