## Title

Next Valid Deployment Key

## Slug

next-valid-deployment-key

## Difficulty

Hard

## Description

A cloud security platform manages deployment keys that must follow strict ordering rules for version control and audit compliance.

You are given two strings `s` and `target`, both having the same length `n` and consisting only of lowercase English letters.

The string `s` represents the pool of characters available for generating a new deployment key, while `target` represents the currently active key in the system.

Your task is to generate a new deployment key by rearranging (permuting) the characters of `s` such that the generated key is lexicographically strictly greater than `target`. Among all such valid permutations, you must return the lexicographically smallest possible one.

If no permutation of `s` can produce a key that is lexicographically strictly greater than `target`, return an empty string.

A string `a` is lexicographically strictly greater than a string `b` (both of the same length) if, at the first position where they differ, the character in `a` appears later in the English alphabet than the corresponding character in `b`.

This process ensures minimal advancement in version ordering while still guaranteeing a strictly increasing deployment sequence.

## Examples

### 1

#### Input

abc  
bba

#### Output

bca

#### Explanation

The permutations of "abc" in lexicographical order are:

"abc", "acb", "bac", "bca", "cab", "cba"

The lexicographically smallest permutation that is strictly greater than "bba" is "bca".

### 2

#### Input

leet  
code

#### Output

eelt

#### Explanation

Among all permutations of "leet", "eelt" is the smallest one that is lexicographically strictly greater than "code".

### 3

#### Input

leet  
codd

#### Output

eelt

## Input Format

- First line: string `s`
- Second line: string `target`

Both strings:
- Have equal length `n`
- Contain only lowercase English letters

## Output Format

- Return a single string — the lexicographically smallest permutation of `s` that is strictly greater than `target`
- If no such permutation exists, return an empty string

## Constraints

- 1 ≤ n ≤ 300  
- `s.length == target.length`  
- `s` and `target` consist only of lowercase English letters  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

greedy  
