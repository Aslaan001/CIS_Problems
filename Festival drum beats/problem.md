## Title

Festival Drum Beats

## Slug

festival-drum-beats

## Difficulty

Medium

## Description

During the annual festival, villagers line up in rows around a sacred tree, each holding a drum. The chief wants the drummers to play in a zigzag rhythm: the first row beats from left to right, the next row beats from right to left, and this alternation continues for every row.

The drummers are arranged in a binary-tree-like structure, where each drummer may have a left and/or right successor in the next row. Your task is to determine the exact order in which the drum beats are heard, level by level, following this zigzag rhythm.

Return the order of beats as a list of lists, where each inner list corresponds to one row of drummers.

## Examples

### 1
#### Input
[8,4,12,2,null,10,null]

#### Output
[[8],[12,4],[2,10]]

#### Explanation

Row 1: [8]

Row 2: [12, 4] (right to left)

Row 3: [2, 10] (left to right, skipping nulls)

### 2
#### Input
[10,5,15,3,7,12,18]

#### Output
[[10],[15,5],[3,7,12,18]]

#### Explanation

Row 1: [10]

Row 2: [15, 5] (right to left)

Row 3: [3, 7, 12, 18] (left to right)

### 3
#### Input
[]

#### Output
[]

## Input Format

A binary tree is given in array form (level-order), where null represents the absence of a node.

Example: [8,4,12,2,null,10,null] represents the tree:

Root = 8

Left child of 8 = 4, Right child of 8 = 12

Left child of 4 = 2, Right child of 4 = null

Left child of 12 = 10, Right child of 12 = null

## Output Format

A list of lists, where each inner list contains the node values of a row, traversed in zigzag order.

## Constraints

- The number of nodes in the tree is in the range [0, 2000].

- -100 ≤ Node.val ≤ 100

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

binary-tree, bfs