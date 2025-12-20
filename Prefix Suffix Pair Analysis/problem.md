## Title

Prefix Suffix Pair Analysis

## Slug

prefix-suffix-pair-analysis

## Difficulty

Hard

## Description

A text processing engine analyzes a sequence of lowercase strings to detect structural relationships between earlier and later entries.

You are given a 0-indexed array of strings called words. The system defines a validation rule between two strings as follows:

A string str1 is considered valid with respect to another string str2 if str1 is both a prefix and a suffix of str2.

For example:
- The string "aba" is both a prefix and a suffix of "ababa".
- The string "abc" is not a suffix of "abcd", so it does not satisfy the condition.

Your task is to count how many index pairs (i, j) satisfy all of the following conditions:
- i < j
- words[i] is both a prefix and a suffix of words[j]

Return the total number of such valid index pairs.

## Examples

### 1

#### Input
4  
a  
aba  
ababa  
aa  

#### Output
4

#### Explanation

Valid pairs are:
(0, 1), (0, 2), (0, 3), and (1, 2)

### 2

#### Input
4  
pa  
papa  
ma  
mama  

#### Output
2

#### Explanation

Valid pairs are:
(0, 1) and (2, 3)

### 3

#### Input
2  
abab  
ab  

#### Output
0

#### Explanation

No index pair satisfies the required prefix and suffix condition.

## Input Format

- First line: integer n, the number of strings
- Next n lines: each line contains one string

## Output Format

- Return a single integer representing the number of valid index pairs

## Constraints

- 1 ≤ n ≤ 100000
- 1 ≤ length of each string ≤ 100000
- All strings contain only lowercase English letters

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

string
