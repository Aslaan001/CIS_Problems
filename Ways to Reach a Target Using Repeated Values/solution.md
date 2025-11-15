## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

long long dp[305][5005];

long long fun(int i, vector<int>& vals, int s, int target) {
    if (s == target) return 1;
    if (s > target || i >= vals.size()) return 0;

    if (dp[i][s] != -1) return dp[i][s];

    // skip current value + take current value again
    return dp[i][s] = fun(i + 1, vals, s, target) + fun(i, vals, s + vals[i], target);
}

long long waysToReachTargetRepeatedValues(int target, vector<int>& vals) {
    memset(dp, -1, sizeof(dp));
    return fun(0, vals, 0, target);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

static long[][] dp;

static long fun(int i, int s, int target, int[] vals) {
    if (s == target) return 1;
    if (s > target || i >= vals.length) return 0;

    if (dp[i][s] != -1) return dp[i][s];

    return dp[i][s] = fun(i + 1, s, target, vals) + fun(i, s + vals[i], target, vals);
}

public static long waysToReachTargetRepeatedValues(int target, int[] vals) {
    dp = new long[vals.length][target + 1];
    for (long[] row : dp) Arrays.fill(row, -1);
    return fun(0, 0, target, vals);
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

long long dp[305][5005];

long long fun(int i, int s, int target, int* vals, int n) {
    if (s == target) return 1;
    if (s > target || i >= n) return 0;

    if (dp[i][s] != -1) return dp[i][s];

    return dp[i][s] = fun(i + 1, s, target, vals, n) + fun(i, s + vals[i], target, vals, n);
}

long long waysToReachTargetRepeatedValues(int target, int* vals, int n) {
    memset(dp, -1, sizeof(dp));
    return fun(0, 0, target, vals, n);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function waysToReachTargetRepeatedValues(target, vals) {
  const dp = Array(vals.length)
    .fill(0)
    .map(() => Array(target + 1).fill(-1n));

  function fun(i, s) {
    if (s === target) return 1n;
    if (s > target || i >= vals.length) return 0n;

    if (dp[i][s] !== -1n) return dp[i][s];

    dp[i][s] = fun(i + 1, s) + fun(i, s + vals[i]);
    return dp[i][s];
  }

  return fun(0, 0).toString();
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

from functools import lru_cache

def ways_to_reach_target_repeated_values(target, vals):
    @lru_cache(None)
    def fun(i, s):
        if s == target:
            return 1
        if s > target or i == len(vals):
            return 0
        return fun(i + 1, s) + fun(i, s + vals[i])

    return fun(0, 0)

### METADATA

TimeLimit  
1000

MemoryLimit  
512
