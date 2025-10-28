## Title
Insert Node at K-th Position in a Doubly Linked List

## Slug
insert-node-at-kth-position-in-doubly-linked-list

## Difficulty
Easy

## Description

You are given the `head` of a doubly linked list, an integer `data`, and an integer `k`.

Your task is to insert a new node with the value `data` at the `k`-th position in the list and return the `head` of the updated list.

A doubly linked list node has three fields: `val` (the data), `next` (a pointer to the next node), and `prev` (a pointer to the previous node).

`Details:`
* Positions are 1-indexed. A position `k=1` means inserting at the beginning, and the new node will become the new head.
* If the list has `n` nodes, a position `k=n+1` means inserting at the end of the list.
* If the list is initially empty (`head` is `null`), the new node is inserted as the head, regardless of `k` (though `k` will be 1).

## Examples

### 1

#### Input
4
1 2 3 5
4
4

#### Output
1 2 3 4 5

#### Explanation
The initial list is: `1 <-> 2 <-> 3 <-> 5`.
We need to insert the value `4` at position `k=4`.
The node `5` is currently at position 4. The new node `4` is inserted *before* it.
The new list becomes: `1 <-> 2 <-> 3 <-> 4 <-> 5`.

### 2

#### Input
2
10 20
5
1

#### Output
5 10 20

#### Explanation
The initial list is: `10 <-> 20`.
We need to insert the value `5` at position `k=1`.
The new node becomes the head.
The new list becomes: `5 <-> 10 <-> 20`.

### 3

#### Input
2
100 200
300
3

#### Output
100 200 300

#### Explanation
The initial list is: `100 <-> 200`. The list size `n` is 2.
We need to insert the value `300` at position `k=3` (which is `n+1`).
This means inserting at the end of the list.
The new list becomes: `100 <-> 200 <-> 300`.


## Input Format
-   First line: integer `n` — number of nodes in the initial linked list.
-   Second line: `n` integers representing the node values. This line is empty if `n=0`.
-   Third line: integer `data` — the value of the new node to insert.
-   Fourth line: integer `k` — the position (1-indexed) where the new node should be inserted.

## Output Format
Print the data of all nodes in the modified linked list, separated by a single space.

## Constraints
0 <= n <= 1000
1 <= k <= n + 1
0 <= node.val, data <= 1000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
linked-list, doubly-linked-list, insertion