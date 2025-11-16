## Title
Binary Removal

## Slug
binary-removal

## Difficulty
Easy

## Description
You are given a binary string where adjacent identical characters cancel each other out. This process repeats until no two adjacent characters are the same.

Given the initial binary string s, simulate this cancellation process until no more removals are possible and report the final stabilized string. It can be shown the result is unique regardless of the order of removals.

## Examples

### 1
#### Input
110

#### Output
0

#### Explanation
Remove "11" → "0".

### 2
#### Input
100011

#### Output
10

#### Explanation
Remove "00" → "1011"; then remove "11" → "10".

### 3
#### Input
10011

#### Output
1

#### Explanation
Removing "00" results in "111". Then, one pair of "11" is removed, leaving "1".
This example shows how a removal can create a new pair of adjacent identical characters.

## Input Format
- A single line containing the binary string s consisting only of characters '0' and '1'.

## Output Format
- Print a single line: the final string after repeatedly removing adjacent equal pairs until no more removals can be made.

## Constraints
- 1 ≤ |s| ≤ 10^5
- s consists only of characters '0' and '1'

## Time Limit
1 second

## Memory Limit
256 MB

## Tags 
strings, stack, greedy