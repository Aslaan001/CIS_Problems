## Title
The Dual Value Stabilization

## Slug
the-dual-value-stabilization

## Difficulty
Hard

## Description
In a controlled system, there are n numbered containers arranged in a row.  
Initially, each container holds a unique value, and the system state is represented by an array a of length n, where a[i] = i.

There exists an unknown but fixed function f that takes two positive integers and returns a positive integer.  
The exact rule of this function is not known in advance, but it is guaranteed to be consistent: for the same pair of inputs, the output is always the same.

You are allowed to perform a sequence of operations on the system. In each operation:

- Two indices x and y are selected.
- A temporary value t = f(a[x], a[y]) is computed.
- Both a[x] and a[y] are simultaneously replaced with the value t.

The temporary value is only used during that operation.

Your goal is to carefully choose a sequence of index pairs so that, after all operations are completed, the final array a contains at most two distinct values.

This requirement must be satisfied for every possible definition of the function f.

Determine any valid sequence of operations that guarantees this condition.

## Examples

### 1
#### Input
3

#### Output
2
1 2
2 3

### 2
#### Input
4

#### Output
8
1 2
3 4
1 3
2 4
1 2
3 4
1 3
2 4

## Input Format
- A single integer n representing the size of the array.

## Output Format
- First line contains an integer q, the number of operations.
- Each of the next q lines contains two integers x and y describing one operation.

## Constraints
- 1 ≤ n ≤ 15000
- 0 ≤ q ≤ 500000
- 1 ≤ x, y ≤ n

## Time Limit
3 seconds

## Memory Limit
256 megabytes


## Tags
recursion, hackwithinfy

## Company
infosys
