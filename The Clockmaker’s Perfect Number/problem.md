## Title
The Clockmaker’s Perfect Number

## Slug
the-clockmakers-perfect-number

## Difficulty
Hard

## Description
A legendary clockmaker is designing a new kind of mechanical clock powered entirely by numbers.  
For the clock to work flawlessly, it must be initialized with a perfect number string.

You are given a string num representing a positive integer, and a positive integer t.

A number string is considered zero-free if none of its digits are 0.

The clockmaker defines a number as perfect if:
- It is zero-free  
- It is greater than or equal to num  
- The product of its digits is divisible by t  

Your task is to help the clockmaker find the smallest such perfect number.

If no zero-free number greater than or equal to num satisfies the condition, return -1.

## Examples

### 1
#### Input
1234 256

#### Output
1488

#### Explanation
1488 is zero-free, greater than 1234, and  
1 × 4 × 8 × 8 = 256, which is divisible by 256.

### 2
#### Input
12355 50

#### Output
12355

#### Explanation
12355 is already zero-free and  
1 × 2 × 3 × 5 × 5 = 150, which is divisible by 50.

## Input Format
- A string num representing a positive integer with no leading zeros  
- An integer t  

## Output Format
Return a string representing the smallest zero-free number greater than or equal to num whose digit product is divisible by t.  
If no such number exists, return -1.

## Constraints
2 ≤ length of num ≤ 2·10^5  
num consists only of digits from 0 to 9  
1 ≤ t ≤ 10^14  

## Time Limit
3 seconds

## Memory Limit
512 megabytes

## Tags
recursion,dynamic-programming, hackwithinfy

## Company
infosys
