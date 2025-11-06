## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int bitwiseOrOfEvenNumbers(vector<int>& nums) {
    int result = 0;
    for (int num : nums) {
        if (num % 2 == 0) result |= num;
    }
    return result;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION


public static int bitwiseOrOfEvenNumbers(int[] nums) {
        int result = 0;
        for (int num : nums) {
            if (num % 2 == 0) result |= num;
        }
        return result;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

#include <stdio.h>
#include <stdlib.h>

int bitwiseOrOfEvenNumbers(int* nums, int n) {
    int result = 0;
    for (int i = 0; i < n; i++) {
        if (nums[i] % 2 == 0) result |= nums[i];
    }
    return result;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function bitwiseOrOfEvenNumbers(nums) {
  let result = 0;
  for (const num of nums) {
    if (num % 2 === 0) result |= num;
  }
  return result;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def bitwise_or_of_even_numbers(nums):
    result = 0
    for num in nums:
        if num % 2 == 0:
            result |= num
    return result

### METADATA

TimeLimit
1000

MemoryLimit
512
