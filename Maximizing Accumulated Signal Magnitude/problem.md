## Title
Maximizing Accumulated Signal Magnitude

## Slug
maximizing-accumulated-signal-magnitude

## Difficulty
Hard

## Description
A data processing system receives a sequence of signed integer signals over time.  
The system maintains a running value c, which is initially set to 0.

For each signal ai in the sequence (processed from left to right), the system must choose exactly one of the following operations:

- Add the signal directly to the current value, updating c to c + ai.
- Add the signal and then normalize the result by taking its absolute value, updating c to |c + ai|.

After processing all signals, the system ends with a final value of c.

Let k be the maximum possible final value of c that can be obtained by choosing the operations optimally.  
Your task is to determine how many distinct sequences of choices (procedures) result in this maximum final value k.

Two procedures are considered different if, at any position, one procedure applies normalization and the other does not, even if the intermediate values of c are the same.

Since the number of such procedures can be very large, output the result modulo 998244353.

## Examples

### 1
#### Input
4  
2 -5 3 -3  

#### Output
12  

#### Explanation
The maximum achievable final value is 3.  
There are multiple ways to apply normalization at different positions to reach this value, resulting in 12 distinct procedures.

### 2
#### Input
8  
1 4 3 4 1 4 3 4  

#### Output
256  

#### Explanation
In this case, applying normalization never changes the value of c, so each step has two valid choices, resulting in 2^8 = 256 procedures.

## Input Format
- The first line contains a single integer n — the number of signals.
- The second line contains n integers a1, a2, …, an representing the signal values.

## Output Format
Return a single integer — the number of distinct procedures that result in the maximum possible final value k, modulo 998244353.

## Constraints
- 2 ≤ n ≤ 2 × 10^5  
- −10^9 ≤ ai ≤ 10^9  
- The sum of n over all test cases does not exceed 3 × 10^5  

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
maths, hackwithinfy

## Company
infosys
