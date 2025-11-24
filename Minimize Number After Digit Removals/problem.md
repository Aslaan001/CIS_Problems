## Title

Minimize Number After Digit Removals

## Slug

minimize-number-after-removals

## Difficulty

Medium

## Description

You are given a numeric string s representing a positive whole number.  
Your task is to remove exactly k digits from this string so that the resulting number becomes as small as possible.

Digits may be removed from any position in the string.  
After removals, the final number must not contain leading zeros, except when the entire number becomes "0".

Return the smallest possible number as a string.

## Examples

### 1

#### Input
1432219
3

#### Output
1219

#### Explanation
Removing the digits 4, 3, and 2 gives the smallest remaining number 1219.

### 2

#### Input
10200
1

#### Output
200

#### Explanation
Removing the leading 1 yields 0200, which becomes 200 after trimming leading zeros.

### 3

#### Input
10
2

#### Output
0

#### Explanation
Removing all digits results in an empty number, interpreted as 0.

## Input Format

- First value: string s — the number to minimize.  
- Second value: integer k — the number of digits to remove.

## Output Format

- Return a string representing the smallest possible number after removing k digits.

## Constraints

- 1 ≤ k ≤ |s| ≤ 100000  
- s contains only digits  
- s does not have leading zeros unless it is exactly "0"

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

greedy, stack, strings, monotonic-stack


## Company

Make My Trip