## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int dp[305][305];

int solve(vector<int>& vals, int l, int r) {
    if (l > r) return 0;
    if (dp[l][r] != -1) return dp[l][r];
    int ans = 0;
    for (int i = l; i <= r; i++) {
        int coins = vals[l - 1] * vals[i] * vals[r + 1] + solve(vals, l, i - 1) + solve(vals, i + 1, r);
        ans = max(ans, coins);
    }
    return dp[l][r] = ans;
}

int maximumCoinsFromBurstingBalloons(vector<int>& vals) {
    int n = vals.size();
    vals.insert(vals.begin(), 1);
    vals.push_back(1);
    memset(dp, -1, sizeof(dp));
    return solve(vals, 1, n);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

static int[][] dp;

static int solve(int[] vals, int l, int r) {
    if (l > r) return 0;
    if (dp[l][r] != -1) return dp[l][r];
    int ans = 0;
    for (int i = l; i <= r; i++) {
        int coins = vals[l - 1] * vals[i] * vals[r + 1] + solve(vals, l, i - 1) + solve(vals, i + 1, r);
        ans = Math.max(ans, coins);
    }
    return dp[l][r] = ans;
}

public static int maximumCoinsFromBurstingBalloons(int[] vals) {
    int n = vals.length;
    int[] extended = new int[n + 2];
    extended[0] = 1;
    extended[n + 1] = 1;
    for (int i = 0; i < n; i++) extended[i + 1] = vals[i];
    dp = new int[n + 2][n + 2];
    for (int[] row : dp) Arrays.fill(row, -1);
    return solve(extended, 1, n);
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

int dp[305][305];

int solve(int* vals, int l, int r) {
    if (l > r) return 0;
    if (dp[l][r] != -1) return dp[l][r];
    int ans = 0;
    for (int i = l; i <= r; i++) {
        int coins = vals[l - 1] * vals[i] * vals[r + 1] + solve(vals, l, i - 1) + solve(vals, i + 1, r);
        if (coins > ans) ans = coins;
    }
    return dp[l][r] = ans;
}

int maximumCoinsFromBurstingBalloons(int* vals, int n) {
    int arr[n + 2];
    arr[0] = 1;
    arr[n + 1] = 1;
    for (int i = 0; i < n; i++) arr[i + 1] = vals[i];
    memset(dp, -1, sizeof(dp));
    return solve(arr, 1, n);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function maximumCoinsFromBurstingBalloons(vals) {
  const n = vals.length;
  const nums = [1, ...vals, 1];
  const dp = Array.from({ length: n + 2 }, () => Array(n + 2).fill(-1));

  function solve(l, r) {
    if (l > r) return 0;
    if (dp[l][r] !== -1) return dp[l][r];
    let ans = 0;
    for (let i = l; i <= r; i++) {
      const coins = nums[l - 1] * nums[i] * nums[r + 1] + solve(l, i - 1) + solve(i + 1, r);
      ans = Math.max(ans, coins);
    }
    return (dp[l][r] = ans);
  }

  return solve(1, n);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

from functools import lru_cache

def maximum_coins_from_bursting_balloons(vals):
    nums = [1] + vals + [1]
    n = len(vals)

    @lru_cache(None)
    def solve(l, r):
        if l > r:
            return 0
        ans = 0
        for i in range(l, r + 1):
            coins = nums[l - 1] * nums[i] * nums[r + 1] + solve(l, i - 1) + solve(i + 1, r)
            ans = max(ans, coins)
        return ans

    return solve(1, n)

### METADATA

TimeLimit  
1000

MemoryLimit  
512
