## Title

Height Mismatch Counter

## Slug

height-mismatch-counter

## Difficulty

Easy

## Decsription

During a school photo session, students must line up in a single row such that their heights appear in non-decreasing order. You are given an array `heights`, where each element represents the height of a student standing in the current lineup. To determine how many students are not positioned correctly, compare this lineup with the correctly ordered version of the same list. The correct arrangement, referred to as `expected`, is simply the sorted form of `heights`. Your task is to count how many positions differ between the current lineup and the expected one. This identifies how many students would need to move to achieve the required height order.


## Examples

### 1

#### Input

heights = [1, 1, 4, 2, 1, 3]

#### Output

3

#### Explanation

Sorted order is `[1, 1, 1, 2, 3, 4]`. Mismatched indices are 2, 4, and 5.

### 2

#### Input

heights = [5, 1, 2, 3, 4]

#### Output

5

#### Explanation

All elements differ from their sorted positions.

### 3

#### Input

heights = [1, 2, 3, 4, 5]

#### Output

0

#### Explanation

Already sorted, so no mismatches.

## Input Format

- A single line containing an integer array `heights`.
- Array length ranges from 1 to 100.
- Each element is an integer in the range 1 to 100.

## Output Format

- Return a single integer representing the number of indices where `heights[i] != expected[i]`.

## Constraints

- 1 ≤ heights.length ≤ 100
- 1 ≤ heights[i] ≤ 100
- Sorting must preserve non-decreasing order
- No additional memory constraints beyond standard limits

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

array, sorting
