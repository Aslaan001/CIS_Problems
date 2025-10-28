## Title
Reverse Linked List 2

## Slug
reverse-linked-list-2

## Difficulty
Medium

## Description

Given the `head` of a singly linked list and two integers `m` and `n`, reverse the nodes of the list from position `m` to position `n`.

`Details:`
* Positions are 1-indexed (i.e., `m=1` is the head node).
* It is guaranteed that `1 <= m <= n <= length` of the list.

## Examples

### 1

#### Input
5
1 2 3 4 5
2 4

#### Output
1 4 3 2 5

#### Explanation
The initial list is: `1 -> 2 -> 3 -> 4 -> 5`.
We need to reverse the sublist from position 2 to 4.
The sublist `2 -> 3 -> 4` becomes `4 -> 3 -> 2`.
The final list is: `1 -> 4 -> 3 -> 2 -> 5`.

### 2

#### Input
3
1 2 3
1 3

#### Output
3 2 1

#### Explanation
The initial list is: `1 -> 2 -> 3`.
We need to reverse from position 1 to 3.
The final list is: `3 -> 2 -> 1`.

### 3

#### Input
1
5
1 1

#### Output
5

#### Explanation
The list is: `5`.
Reversing from position 1 to 1 changes nothing.
The final list is: `5`.

## Input Format
-   First line: integer `n` — number of nodes in the linked list.
-   Second line: `n` integers representing the node values.
-   Third line: two integers `m` and `n` — the start and end positions for reversal.

## Output Format
For each test case, print the data of all nodes in the modified linked list on a new line, separated by a single space.

## Constraints
- 1 <= n <= 500
- 1 <= m <= n
- -5000 <= node.val <= 5000

## Time Limit
1 second

## Memory Limit
512 MB

## Tags
linked-list, two-pointers, reversal