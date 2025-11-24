
## Title

Greatest Common Dividing String

## Slug

greatest-common-dividing-string

## Difficulty

Easy

## Description

For two strings `s` and `t` , we say that “t divides s” if and only if `s` can be formed by concatenating `t` with itself one or more times.
Given two strings `str1` and `str2`, your task is to determine the `largest string` `x` such that `x` divides both `str1` and `str2`.

If no such string exists, return an empty string `""`.

## Examples

### 1

#### Input

str1 = "ABCABC", str2 = "ABC"

#### Output

"ABC"

### 2

#### Input

str1 = "ABABAB", str2 = "ABAB"

#### Output

"AB"

### 3

#### Input

str1 = "LEET", str2 = "CODE"

#### Output

""

## Input Format

- Two lines of input, each containing a string:

  - `str1` — a string of uppercase English letters
  - `str2` — a string of uppercase English letters

## Output Format

- Return a string `x` representing the largest string that divides both `str1` and `str2`.

## Constraints

- 1 ≤ str1.length, str2.length ≤ 1000
- Strings consist only of uppercase English letters
- Return an empty string if no common divisor string exists

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

string, maths


