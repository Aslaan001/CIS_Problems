## Title

Binary Signal Aggregation

## Slug

binary-signal-aggregation

## Difficulty

Easy

## Description

A low-level communication system represents numerical values using binary strings.  
Each binary string consists only of characters `0` and `1` and does not contain leading zeros, except when the value itself is zero.

You are given two binary strings `a` and `b`, each representing a non-negative integer in binary form.

Your task is to compute the sum of these two binary values and return the result as a binary string, also without leading zeros.

This operation simulates binary addition as performed at the hardware or protocol level.

## Examples

### 1

#### Input

11  
1

#### Output

100

#### Explanation

Binary addition:

- 11 (3 in decimal)  
- 1 (1 in decimal)  

Sum = 4 → binary representation is 100.

### 2

#### Input

1010  
1011

#### Output

10101

#### Explanation

Binary addition:

- 1010 (10 in decimal)  
- 1011 (11 in decimal)  

Sum = 21 → binary representation is 10101.

## Input Format

- First line contains a binary string `a`.
- Second line contains a binary string `b`.

## Output Format

- Return a single binary string representing the sum of `a` and `b`.

## Constraints

- 1 ≤ length of `a`, `b` ≤ 10000  
- `a` and `b` consist only of characters `0` and `1`  
- No leading zeros except for the string `"0"`

## Time Limit

1 second

## Memory Limit

512 MB


## Tags

string  

## Company

snapchat
