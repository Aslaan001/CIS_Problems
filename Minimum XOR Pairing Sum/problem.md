## Title

Minimum XOR Pairing Sum

## Slug

minimum-xor-pairing-sum

## Difficulty

Hard

## Description

You are given two integer arrays nums1 and nums2 of equal length n.

You may rearrange the elements of nums2 in any order.  
After rearrangement, define the XOR sum as:

(nums1[0] XOR nums2[0])  
+ (nums1[1] XOR nums2[1])  
+ ...  
+ (nums1[n - 1] XOR nums2[n - 1])

Your task is to permute nums2 so that this total XOR sum is minimized.

Return the minimum possible XOR sum.

## Examples

### 1

#### Input
2
1 2  
2 3

#### Output
2

#### Explanation

One optimal rearrangement of nums2 is [3, 2].  
The XOR sum becomes:

(1 XOR 3) + (2 XOR 2) = 2 + 0 = 2.

### 2

#### Input
3
1 0 3  
5 3 4

#### Output
8

#### Explanation

An optimal rearrangement is nums2 = [5, 4, 3].  
The XOR sum is:

(1 XOR 5) + (0 XOR 4) + (3 XOR 3) = 4 + 4 + 0 = 8.

## Input Format

- Array nums1 of length n  
- Array nums2 of length n  

## Output Format

- Return the minimum total XOR sum achievable after reordering nums2.

## Constraints

- 1 ≤ n ≤ 14  
- n = nums1.length = nums2.length  
- 0 ≤ nums1[i], nums2[i] ≤ 10^7  
- Answer fits in 32-bit integer

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

BitmaskDP
