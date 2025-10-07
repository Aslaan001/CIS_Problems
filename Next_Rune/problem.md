## Title

The Next Rune


## Slug

next-rune

## Difficulty

Easy

## Description

In the land of Lexiconia, ancient runes are arranged in a sacred circle.
Each rune is a lowercase English letter, and the sequence of runes is always sorted in non-decreasing order.

A wandering scribe seeks the next rune that comes after a given target rune in lexicographic order.
If no rune in the circle is greater than the target, the scribe must wrap around to the first rune in the sequence — because in Lexiconia, the runes form an eternal loop.

Can you help the scribe find the next rune for a given target?

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
- Second line: `n` space-separated lowercase English letters representing the runes (sorted in non-decreasing order).  
- Third line: a single lowercase English letter — the target rune.

## Output Format  

- Print the **smallest rune** that is lexicographically greater than the target.  
- If no such rune exists, print the **first rune** in the sequence.  



## Constraints  

- 2 ≤ n ≤ 10⁴  
- Each rune is a lowercase English letter (`'a'` to `'z'`).  
- The list contains at least two distinct runes. 

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

binary-search, arrays, strings, simulation 