## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

long long maxAlternatingPower(vector<int>& nums) {
    for (auto &a : nums) a = abs(a);
    sort(nums.rbegin(), nums.rend());
    int n = nums.size();
    long long ans = 0;
    for (int i = 0; i < n / 2; i++) {
        ans += 1LL * nums[i] * nums[i];
    }
    if (n % 2 != 0) {
        ans += 1LL * nums[n / 2] * nums[n / 2];
    }
    int s = (n % 2 != 0) ? (n / 2 + 1) : (n / 2);
    for (int i = s; i < n; i++) {
        ans -= 1LL * nums[i] * nums[i];
    }
    return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

import java.util.*;

public static long maxAlternatingPower(int[] nums) {
        for (int i = 0; i < nums.length; i++) nums[i] = Math.abs(nums[i]);
        Arrays.sort(nums);
        int n = nums.length;
        long ans = 0;
        for (int i = n - 1; i >= n / 2; i--) {
            ans += 1L * nums[i] * nums[i];
        }
        if (n % 2 != 0) {
            ans += 1L * nums[n / 2] * nums[n / 2];
        }
        int s = (n % 2 != 0) ? (n / 2 + 1) : (n / 2);
        for (int i = s; i < n / 2; i++) {
            ans -= 1L * nums[i] * nums[i];
        }
        return ans;
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

int cmpdesc(const void* a, const void* b) {
    return (*(int*)b - *(int*)a);
}

long long maxAlternatingPower(int* nums, int n) {
    for (int i = 0; i < n; i++) {
        if (nums[i] < 0) nums[i] = -nums[i];
    }
    qsort(nums, n, sizeof(int), cmpdesc);
    long long ans = 0;
    for (int i = 0; i < n / 2; i++) {
        ans += 1LL * nums[i] * nums[i];
    }
    if (n % 2 != 0) {
        ans += 1LL * nums[n / 2] * nums[n / 2];
    }
    int s = (n % 2 != 0) ? (n / 2 + 1) : (n / 2);
    for (int i = s; i < n; i++) {
        ans -= 1LL * nums[i] * nums[i];
    }
    return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function maxAlternatingPower(nums) {
  nums = nums.map(x => Math.abs(x));
  nums.sort((a, b) => b - a);
  const n = nums.length;
  let ans = 0n;
  for (let i = 0; i < Math.floor(n / 2); i++) {
    ans += BigInt(nums[i]) * BigInt(nums[i]);
  }
  if (n % 2 !== 0) {
    ans += BigInt(nums[Math.floor(n / 2)]) * BigInt(nums[Math.floor(n / 2)]);
  }
  let s = n % 2 !== 0 ? Math.floor(n / 2) + 1 : Math.floor(n / 2);
  for (let i = s; i < n; i++) {
    ans -= BigInt(nums[i]) * BigInt(nums[i]);
  }
  return ans;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def max_alternating_power(nums):
    nums = [abs(x) for x in nums]
    nums.sort(reverse=True)
    n = len(nums)
    ans = 0
    for i in range(n // 2):
        ans += nums[i] * nums[i]
    if n % 2 != 0:
        ans += nums[n // 2] * nums[n // 2]
    s = n // 2 + 1 if n % 2 != 0 else n // 2
    for i in range(s, n):
        ans -= nums[i] * nums[i]
    return ans

### METADATA

TimeLimit
1000

MemoryLimit
512
