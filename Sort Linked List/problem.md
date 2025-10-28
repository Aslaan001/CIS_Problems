## Title
Sort Linked List

## Slug
sort-linked-list

## Difficulty
Medium

## Description

Given the `head` of a singly linked list, sort the list in ascending order and return the `head` of the sorted list.

## Examples

### 1

#### Input
4
4 2 1 3

#### Output
1 2 3 4

#### Explanation
The initial list is: `4 -> 2 -> 1 -> 3`.
After sorting, the list becomes: `1 -> 2 -> 3 -> 4`.

### 2

#### Input
5
-1 5 3 4 0

#### Output
-1 0 3 4 5

#### Explanation
The initial list is: `-1 -> 5 -> 3 -> 4 -> 0`.
After sorting, the list becomes: `-1 -> 0 -> 3 -> 4 -> 5`.


## Input Format
-   First line: integer `n` — number of nodes in the linked list.
-   Second line: `n` integers representing the node values. This line is empty if `n=0`.

## Output Format
For each test case, print the data of all nodes in the sorted linked list on a new line, separated by a single space.

## Constraints
0 <= n <= 50000
-100000 <= node.val <= 100000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
linked-list, sorting, two-pointers, merge-sort