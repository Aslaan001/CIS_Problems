## Title

Research Paper Impact Index

## Slug

research-paper-impact-index

## Difficulty

Medium

## Description

A research institute wants to measure the impact of its researchers based on their publication records.  
Each researcher’s paper record is represented as an array `citations`, where `citations[i]` denotes the number of citations received by the i-th paper.

The institute defines the impact index as follows:

A researcher has an index `h` if `h` of their papers have at least h citations each, and the remaining papers have no more than h citations.

Your task is to compute the maximum value of `h` that satisfies this condition.

Return the researcher’s H-index.

## Examples

### 1

#### Input
5  
3 0 6 1 5

#### Output
3

#### Explanation
There are 3 papers with at least 3 citations each.  
The remaining papers have fewer than or equal to 3 citations.

### 2

#### Input
3  
1 3 1

#### Output
1

#### Explanation
Only one paper has at least one citation.

## Input Format

First line contains an integer n — the number of papers.  
Second line contains n space-separated integers representing the citation counts.

## Output Format

Return the H-index value.

## Constraints

1 ≤ n ≤ 5000  
0 ≤ citations[i] ≤ 1000  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

array, sorting
