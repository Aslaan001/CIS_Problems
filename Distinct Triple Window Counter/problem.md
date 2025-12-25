## Title

Distinct Triple Window Counter

## Slug

distinct-triple-window-counter

## Difficulty

Easy

## Description

A monitoring system analyzes short patterns within a stream of characters to detect diversity in small segments.  
Each character in the stream is a lowercase English letter.

A segment of the stream is considered good if all characters inside the segment are distinct, meaning no character repeats.

You are given a string s.  
Your task is to count how many contiguous substrings of length exactly three are good.

Every occurrence must be counted separately, even if multiple substrings have the same characters.

This task is commonly used in pattern detection, sliding window analysis, and short-sequence validation.

## Examples

### 1

#### Input

xyzzaz

#### Output

1

#### Explanation

All substrings of length 3 are:

- xyz  
- yzz  
- zza  
- zaz  

Only xyz contains all distinct characters.

### 2

#### Input

aababcabc

#### Output

4

#### Explanation

All substrings of length 3 are:

- aab  
- aba  
- bab  
- abc  
- bca  
- cab  
- abc  

The good substrings are:

- abc  
- bca  
- cab  
- abc  

## Input Format

- A single string s

## Output Format

- Return a single integer representing the number of good substrings of length three

## Constraints

- 1 ≤ length of s ≤ 100  
- s consists only of lowercase English letters

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

string  


## Company

quora
