## Title

Are They One Swap Away


## Slug

are-they-one-swap-away

## Difficulty

Easy

## Description

You are given `two strings` of equal length consisting of lowercase English letters.  

Your task is to determine whether the first string can be made equal to the second string by performing `exactly one swap` of two characters in the first string.  

If it is possible, return `"YES"`; otherwise, return `"NO"`.


## Examples

### 1

#### Input

5
abcde
abced

#### Output

YES

#### Explanation

Swapping `'d'` and `'e'` in the first string makes it equal to the second string.

### 2

#### Input

6
xyzzaz
qwdsad

#### Output

NO

#### Explanation

No single swap in the first string can make it equal to the second string.

## Input Format  


- First line: an integer `n` — the length of the strings.  
- Second line: string `s1` of length `n`.  
- Third line: string `s2` of length `n`.

## Output Format  

- A single line: `"YES"` or `"NO"`.



## Constraints  

- 1 ≤ n ≤ 10⁵  
- `s1` and `s2` consist of lowercase English letters only.  


## Time Limit

1 second

## Memory Limit

512 MB

## Tags

strings, swapping.
