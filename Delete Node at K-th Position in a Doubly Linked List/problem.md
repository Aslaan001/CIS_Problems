## Title
Delete Node at K-th Position in a Doubly Linked List

## Slug
delete-node-at-kth-position-in-doubly-linked-list

## Difficulty
Easy

## Description

You are given the `head` of a doubly linked list and an integer `k`.

Your task is to delete the node at the `k`-th position in the list and return the `head` of the updated list.

A doubly linked list node has three fields: `val` (the data), `next` (a pointer to the next node), and `prev` (a pointer to the previous node).

`Details:`
* Positions are 1-indexed.
* A position `k=1` means deleting the head node.
* It is guaranteed that `1 <= k <= n`, where `n` is the number of nodes in the list.

## Examples

### 1

#### Input
5
1 2 3 4 5
3

#### Output
1 2 4 5

#### Explanation
The initial list is: `1 <-> 2 <-> 3 <-> 4 <-> 5`.
We need to delete the node at position `k=3`, which is the node with value `3`.
The new list becomes: `1 <-> 2 <-> 4 <-> 5`.

### 2

#### Input
3
10 20 30
1

#### Output
20 30

#### Explanation
The initial list is: `10 <-> 20 <-> 30`.
We need to delete the node at position `k=1`, which is the head node `10`.
The new head becomes `20`.
The new list becomes: `20 <-> 30`.

### 3

#### Input
4
100 200 300 400
4

#### Output
100 200 300

#### Explanation
The initial list is: `100 <-> 200 <-> 300 <-> 400`.
We need to delete the node at position `k=4`, which is the tail node `400`.
The new tail becomes `300`.
The new list becomes: `100 <-> 200 <-> 300`.


## Input Format
 -   First line: integer `n` — number of nodes in the linked list.
 -   Second line: `n` integers representing the node values.
 -   Third line: integer `k` — the position (1-indexed) of the node to delete.

## Output Format
For each test case, print the data of all nodes in the modified linked list on a new line, separated by a single space. If the list is empty, print an empty line.

## Constraints
1 <= n <= 1000
1 <= k <= n
0 <= node.val <= 1000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
linked-list, doubly-linked-list, deletion