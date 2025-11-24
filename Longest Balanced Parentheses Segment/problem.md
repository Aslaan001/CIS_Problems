## Title

Longest Balanced Parentheses Segment

## Slug

longest-balanced-parentheses-segment

## Difficulty

Hard

## Description

You are given a string made up of the characters '(' and ')'.  
Your task is to determine the length of the longest substring that forms a valid, balanced sequence of parentheses.

A substring is considered balanced if:

- every opening parenthesis '(' has a matching closing parenthesis ')', and  
- parentheses are properly nested.

Return the maximum length of any such substring.

## Examples

### 1

#### Input
(() 

#### Output
2

#### Explanation
The substring "()" is the longest balanced segment.

### 2

#### Input
)()()) 

#### Output
4

#### Explanation
The longest balanced segment is "()()".

### 3

#### Input
()

#### Output
2

## Input Format

- A single string s consisting only of '(' and ')'.

## Output Format

- Return a single integer representing the length of the longest balanced parentheses substring.

## Constraints

- 0 ≤ |s| ≤ 10^5  
- s contains only '(' and ')'

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

stack, dynamic-programming, two-pointers, strings
