## Title

Expression Evaluation Engine

## Slug

expression-evaluation-engine

## Difficulty

Hard

## Description

A financial computation service receives arithmetic expressions as plain text strings.  
These expressions may include:

- Non-negative integers  
- Addition and subtraction operators  
- Nested parentheses for grouping  
- Arbitrary whitespace between tokens  

The service must evaluate each expression and return the final computed integer value.

The evaluation rules follow standard arithmetic precedence defined by parentheses.  
You are not allowed to rely on any built-in expression evaluators or language-level execution helpers.

Unary negation is supported, meaning expressions like `-3` or `-(2 + 5)` are valid.  
Unary addition is not allowed.

All expressions provided are guaranteed to be valid, and intermediate as well as final results will fit within 32-bit signed integer limits.

Your task is to parse the expression manually and compute the correct result.

## Examples

### 1

#### Input

1 + 1

#### Output

2

#### Explanation

The expression evaluates directly to 2.

### 2

#### Input

2-1 + 2

#### Output

3

#### Explanation

Step-by-step evaluation results in 3.

### 3

#### Input

(1+(4+5+2)-3)+(6+8)

#### Output

23

#### Explanation

Nested parentheses are resolved first, then combined to produce the final value.

## Input Format

- A single string `s` representing a valid arithmetic expression

## Output Format

- Return a single integer representing the evaluated result of the expression

## Constraints

- 1 ≤ length of `s` ≤ 300000  
- `s` consists only of digits, spaces, `+`, `-`, `(`, and `)`  
- No two operators appear consecutively  
- Unary `-` is allowed, unary `+` is not allowed  
- Expression is always valid  
- Result fits in 32-bit signed integer range  

## Time Limit

1 second

## Memory Limit

512 MB


## Tags

string

## Company

snapchat