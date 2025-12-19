## Title
Integrity Verification in Alien Communication Logs

## Slug
integrity-verification-in-alien-communication-logs

## Difficulty
Hard

## Description
A research lab is analyzing communication logs obtained from an unknown extraterrestrial source.  
Each log entry is encoded as a positive integer, and these integers are stored sequentially in an array.

To verify the integrity of the communication, the lab examines pairs of log entries.  
For any two entries at positions i and j (where i ≤ j), the system computes the least common multiple (lcm) of their values.

An integrity check passes if this lcm value is a semi-prime number.  
A number is considered semi-prime if it can be expressed as the product of two prime numbers, where the two primes do not have to be distinct.

Your task is to process multiple independent log datasets and, for each dataset, determine how many ordered pairs of indices (i, j) satisfy the integrity condition.

## Examples

### 1
#### Input
4  
2 2 3 4  

#### Output
5 

#### Explanation
There are 5 ordered index pairs (i, j) such that i ≤ j and the least common multiple of the selected values is a semi-prime number.

### 2
#### Input
6  
2 2 3 4 5 6  

#### Output
12  

#### Explanation
Several pairs of log entries produce semi-prime values when their least common multiple is computed.

## Input Format
- The first line contains an integer n — the number of log entries.
- The second line contains n integers a1, a2, …, an representing the encoded log values.

## Output Format
Return a single integer — the number of ordered pairs (i, j) such that i ≤ j and lcm(ai, aj) is a semi-prime number.

## Constraints  
- 2 ≤ n ≤ 2 × 10^5  
- 2 ≤ ai ≤ n  
- The sum of n over all test cases does not exceed 2 × 10^5  

## Time Limit
2 seconds

## Memory Limit
256 megabytes

## Tags
maths, hackwithinfy

## Company
infosys
