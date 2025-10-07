## Title

Next Rune


## Slug

next-rune

## Difficulty

Easy

## Description

In the ancient lands of `Runeria`, there lies a mystical collection of `Runes` — each with a unique power value.  
The Rune Master has given you a sacred task: to select a rune in such a way that chosen rune follow the `Runic Order` (i.e., smallest rune that is lexicographically greater than the target). 

But beware! You cannot simply choose any rune greater to target — you must `Choose the rune which is next greater to target in lexographic order` that obey this ancient rule.

Note:- If no such rune exists simply return the first rune.

Your goal is to determine the `ancient rune` that can be collected by the land of Runeria.

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

- 2 ≤ n ≤ 10⁴  
- Each rune is a lowercase English letter (`'a'` to `'z'`).  
- The list contains at least two distinct runes. 

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

binary-search, arrays, strings. 
