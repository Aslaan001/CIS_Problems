## Title

Good Substrings of Size Three


## Slug

good-substrings-three

## Difficulty

Easy

## Description

In the land of `CipherLand`, there exists a mystical string `s` composed of lowercase letters.  
The String Sage has a challenge for you: count the number of `good substrings` of length `three` in `s`.  

A substring is called `good` if it contains `no repeated characters`.  

Every occurrence of a substring counts separately — even if the same substring appears multiple times.  

Your goal is to determine the total number of good substrings of size three in the string `s`.

## Examples

### 1

#### Input

6
xyzzaz

#### Output

1

#### Explanation

Substrings of size 3: `"xyz"`, `"yzz"`, `"zza"`, `"zaz"`.  
Only `"xyz"` has all distinct characters.

### 2

#### Input

9
aababcabc

#### Output

4

#### Explanation

Substrings of size 3: `"aab"`, `"aba"`, `"bab"`, `"abc"`, `"bca"`, `"cab"`, `"abc"`.  
Good substrings: `"abc"`, `"bca"`, `"cab"`, `"abc"`.

## Input Format  


- First line: integer `n` — the length of the string `s`.  
- Second line: string `s` of length `n` (1 ≤ n ≤ 10000).

## Output Format  

- Return a single integer — the number of good substrings of length 3.



## Constraints  

- 1 ≤ n ≤ 10000
- `s` consists of lowercase English letters.

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

strings, sliding-window.
