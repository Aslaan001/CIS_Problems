## Title
Eldric’s Ancient Archive

## Slug
eldric-ancient-archive


## Difficulty
Medium


## Description
In the mystical city of `Archivium`, Eldric the scholar maintains the `Ancient Archive`, a magical tree of knowledge.  
Each scroll in the archive is enchanted with a unique numeric code, and the archive’s organization follows a special rule:

- For any scroll, all scrolls in its left chamber have smaller codes,  
- All scrolls in its right chamber have larger codes.  

This structure is known as the Binary Search Tree of Wisdom (BST).  

Eldric often needs to retrieve the k-th smallest scroll code — the scroll that ranks k-th in ascending order when all codes are sorted.  

Your task is to help Eldric find this k-th smallest code from the archive.

---
## Examples

### 1
#### Input

## Examples

### 1
#### Input


5
3 1 4 null 2
1

#### Output

1

#### Explanation

All scroll codes in sorted order are [1, 2, 3, 4].  
The 1st smallest code is 1.

### 2

#### Input

8
5 3 6 2 4 null null 1
3

#### Output

3

#### Explanation

All scroll codes in sorted order: [1, 2, 3, 4, 5, 6].  
The 3rd smallest code is 3.


## Input Format  

- First line: integer n — number of nodes in the archive.  
- Second line: n space-separated values representing the tree in level-order (use "null" for missing nodes).  
- Third line: integer k — position (1-indexed) of the scroll code Eldric needs.  

## Output Format  

Return a single integer — the k-th smallest scroll code in the archive. 



## Constraints  

- 1 ≤ n ≤ 10⁴  
- 1 ≤ k ≤ n  
- 0 ≤ Node.val ≤ 10⁴

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

binary-search-tree, inorder-traversal, tree, recursion 
