## Title
Fraction Expression Evaluator

## Slug
fraction-addition-subtraction

## Difficulty
Medium

## Description
You are given a string `expression` describing a sequence of `fraction additions and subtractions`.  
Each term is a proper or improper fraction, and signs `+` or `-` indicate how they combine.

Your task is to compute the `final result`, reduce it to an `irreducible fraction`, and output it in `numerator/denominator` format.

If the result is an integer, represent it as `integer/1`.

The input contains only valid irreducible fractions.

## Examples

### 1
#### Input
expression = "-3/2+3/2"

#### Output
0/1

### 2
#### Input
expression = "1/4+1/6+1/3"

#### Output
3/4

### 3
#### Input
expression = "1/5-2/3"

#### Output
-7/15

## Input Format
- A single string `expression`.

## Output Format
- A single irreducible fraction in string format.

## Constraints
- Expression contains only digits, '/', '+', '-'.
- All input fractions are irreducible.
- Number of fractions: 1 to 10.
- Numerator and denominator range: [1, 10]
- Final result fits in signed 32‑bit integer.

## Time Limit
1 second

## Memory Limit
256 MB

## Tags
string, maths
