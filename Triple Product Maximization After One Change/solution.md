## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

long long maxTripleProduct(vector<int>& nums) {
    for (auto &a : nums) {
        a = abs(a);
    }
    sort(nums.begin(), nums.end());
    int n = nums.size();
    return 1LL * nums[n-1] * nums[n-2] * 100000;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

import java.util.*;

public class Solution {
    public static long maxTripleProduct(int[] nums) {
        for (int i = 0; i < nums.length; i++) {
            nums[i] = Math.abs(nums[i]);
        }
        Arrays.sort(nums);
        int n = nums.length;
        return 1L * nums[n-1] * nums[n-2] * 100000;
    }
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

int cmp(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

long long maxTripleProduct(int* nums, int n) {
    for (int i = 0; i < n; i++) {
        if (nums[i] < 0) nums[i] = -nums[i];
    }
    qsort(nums, n, sizeof(int), cmp);
    return 1LL * nums[n-1] * nums[n-2] * 100000;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function maxTripleProduct(nums) {
  nums = nums.map(x => Math.abs(x));
  nums.sort((a,b)=>a-b);
  const n = nums.length;
  return BigInt(nums[n-1]) * BigInt(nums[n-2]) * 100000n;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def max_triple_product(nums):
    nums = [abs(x) for x in nums]
    nums.sort()
    n = len(nums)
    return nums[-1] * nums[-2] * 100000

### METADATA

TimeLimit
1000

MemoryLimit
512
