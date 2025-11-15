## Title

String Rotation Equivalence

## Slug

string-rotation-equivalence

## Difficulty

Easy

## Description

You are given two strings `s` and `goal`. A `shift` on string `s` consists of moving the leftmost character of `s` to the rightmost position.

For example, if `s = "abcde"`, then after one shift it becomes `"bcdea"`.

Your task is to return `true` if and only if string `s` can become string `goal` after some number of shifts.

## Examples

### 1

#### Input

s = "abcde", goal = "cdeab"

#### Output

true

### 2

#### Input

s = "abcde", goal = "abced"

#### Output

false

### 3

#### Input

s = "aaaa", goal = "aaaa"

#### Output

true

## Input Format

- Two lines of input, each containing a string `s` and `goal`.

## Output Format

- Return `true` if `s` can be rotated to match `goal`, otherwise return `false`.

## Constraints

- 1 ≤ s.length, goal.length ≤ 100
- s and goal consist of lowercase English letters.

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

string
