## Title

Check if Triplet Sum Exists

## Slug

check-if-triplet-sum-exists

## Difficulty

Easy

## Description

You are given an array `arr[]` of `n` integers and an integer `k`.  
Your task is to determine whether there exists `any triplet (i, j, l)` such that: arr[i] + arr[j] + arr[l] = k

If such a triplet exists, print `"YES"`.  
Otherwise, print `"NO"`.



### Example 1

#### Input
6  
1 4 45 6 10 8  
22

#### Output
YES

#### Explanation
The triplet `(4, 8, 10)` sums to `22`.


### Example 2

#### Input
4  
1 2 4 9  
8

#### Output
NO

#### Explanation
No combination of three numbers adds up to `8`.

---

## Input Format

- The first line contains an integer `n` — the number of elements in the array.  
- The second line contains `n` space-separated integers representing the array elements.  
- The third line contains an integer `k` — the required sum.

---

## Output Format

- Return `"YES"` if there exists a triplet whose sum is equal to `k`.  
- Otherwise, return `"NO"`.

---

## Constraints

- 3 ≤ n ≤ 10⁵  
- −10⁶ ≤ arr[i] ≤ 10⁶  
- −10⁶ ≤ k ≤ 10⁶  

---

## Time Limit

1 second

## Memory Limit

512 MB

---

## Tags

arrays, two-pointers.