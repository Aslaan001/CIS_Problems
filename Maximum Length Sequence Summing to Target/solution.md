## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int dp[1002][1002];

int fun(int i, vector<int>& nums, int s, int target) {
    if (s == target) return 0;
    if (s > target || i >= nums.size()) return -1000000000;
    if (dp[i][s] != -1) return dp[i][s];
    int a = 1 + fun(i + 1, nums, s + nums[i], target);
    int b = fun(i + 1, nums, s, target);
    return dp[i][s] = max(a, b);
}

int maximumLengthSequenceSummingToTarget(vector<int>& nums, int target) {
    memset(dp, -1, sizeof(dp));
    int k = fun(0, nums, 0, target);
    if (k < 0) return -1;
    return k;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

static int[][] dp;

static int fun(int i, int s, int target, int[] nums) {
    if (s == target) return 0;
    if (s > target || i >= nums.length) return -1000000000;
    if (dp[i][s] != -1) return dp[i][s];
    int a = 1 + fun(i + 1, s + nums[i], target, nums);
    int b = fun(i + 1, s, target, nums);
    return dp[i][s] = Math.max(a, b);
}

public static int maximumLengthSequenceSummingToTarget(int[] nums, int target) {
    dp = new int[nums.length + 1][target + 1];
    for (int[] row : dp) Arrays.fill(row, -1);
    int k = fun(0, 0, target, nums);
    if (k < 0) return -1;
    return k;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

#include <stdio.h>
#include <string.h>

int dp[1002][1002];

int fun(int i, int s, int target, int* nums, int n) {
    if (s == target) return 0;
    if (s > target || i >= n) return -1000000000;
    if (dp[i][s] != -1) return dp[i][s];
    int a = 1 + fun(i + 1, s + nums[i], target, nums, n);
    int b = fun(i + 1, s, target, nums, n);
    dp[i][s] = a > b ? a : b;
    return dp[i][s];
}

int maximumLengthSequenceSummingToTarget(int* nums, int n, int target) {
    memset(dp, -1, sizeof(dp));
    int k = fun(0, 0, target, nums, n);
    if (k < 0) return -1;
    return k;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function maximumLengthSequenceSummingToTarget(nums, target) {
  const dp = Array(nums.length + 1).fill(0).map(() => Array(target + 1).fill(undefined));

  function fun(i, s) {
    if (s === target) return 0;
    if (s > target || i >= nums.length) return -1000000000;
    if (dp[i][s] !== undefined) return dp[i][s];
    const a = 1 + fun(i + 1, s + nums[i]);
    const b = fun(i + 1, s);
    return (dp[i][s] = Math.max(a, b));
  }

  const k = fun(0, 0);
  if (k < 0) return -1;
  return k;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

from functools import lru_cache

def maximum_length_sequence_summing_to_target(nums, target):
    @lru_cache(None)
    def fun(i, s):
        if s == target:
            return 0
        if s > target or i == len(nums):
            return -10**9
        return max(1 + fun(i + 1, s + nums[i]), fun(i + 1, s))

    k = fun(0, 0)
    if k < 0:
        return -1
    return k

### METADATA

TimeLimit  
1000

MemoryLimit  
512
