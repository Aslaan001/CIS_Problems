## Title  
Lexicographically Minimum String After Removing Stars  

## Slug  
lexicographically-minimum-string-after-removing-stars  

## Difficulty  
Medium  

## Description  

A text processing system logs characters exactly as they are typed by a user.  
Occasionally, the system inserts a special correction marker `*` to indicate that a cleanup operation must be performed.

Each time a `*` appears, the system applies the following rule:

- The `*` character itself is removed.
- Along with it, one previously typed character located to the left of the `*` is also removed.
- To maintain the smallest possible alphabetical order in the final text, the system always removes the smallest lexicographical character available to the left of that `*`.
- If multiple smallest characters exist, any one of them may be removed.

This process continues until all `*` characters have been removed.

Your task is to simulate this correction mechanism and return the lexicographically smallest possible final string.

It is guaranteed that the input is valid, meaning every `*` will always have at least one removable character to its left.

## Examples  

### 1  

#### Input  
aaba*  

#### Output  
aab  

#### Explanation  

One of the characters `'a'` to the left of `*` is removed.  
Removing the rightmost `'a'` results in the smallest possible string.  

### 2  

#### Input  
abc  

#### Output  
abc  

#### Explanation  

There are no correction markers, so the string remains unchanged.  

## Input Format  

- The first line contains an integer T — the number of test cases.  
- Each of the next T lines contains a string s.  

## Output Format  

For each test case, output the resulting string after all correction operations are applied.  

## Constraints  

1 ≤ T ≤ 10  
1 ≤ length of s ≤ 100000  
s contains only lowercase English letters and `*`  
All `*` characters can be successfully removed  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

priority-queue  
