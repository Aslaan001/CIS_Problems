## Title

Next Rune


## Slug

next-rune

## Difficulty

Easy

## Description

In an ancient kingdom, powerful runes were inscribed to hold mystical powers. Each rune is represented by a character. You are given a sorted list of runes and a target rune. Your task is to find the smallest rune that is lexicographically greater than the target. If no such rune exists, return the first rune in the list.

## Examples

### 1

#### Input

3
c f j
a

#### Output

c

#### Explanation

The next rune greater than `'a'` is `'c'`.

### 2

#### Input

3
c f j
c

#### Output

f

#### Explanation

The next rune greater than `'c'` is `'f'`.  

## Input Format  

- First line: an integer `n` — the number of runes.  
- Second line: `n` space-separated lowercase English letters representing the runes (sorted in non-decreasing order) stored in array.  
- Third line: a single lowercase English letter — the target rune.

## Output Format  

- Return the `smallest rune` that is lexicographically greater than the target.  
- If no such rune exists, return the `first rune` in the sequence.  



## Constraints  

- 2 ≤ n ≤ 1e5  
- Each rune is a lowercase English letter (`'a'` to `'z'`).  
- The list contains at least two distinct runes. 

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

binary-search, arrays, strings. 
