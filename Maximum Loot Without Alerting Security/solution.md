## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int maximumLootWithoutAlertingSecurity(vector<int>& vals) {
    int n = vals.size();
    if (n == 0) return 0;
    if (n == 1) return vals[0];

    vector<int> dp(n);
    dp[0] = vals[0];
    dp[1] = max(vals[0], vals[1]);

    for (int i = 2; i < n; i++) {
        dp[i] = max(dp[i - 1], dp[i - 2] + vals[i]);
    }

    return dp[n - 1];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int maximumLootWithoutAlertingSecurity(int[] vals) {
    int n = vals.length;
    if (n == 0) return 0;
    if (n == 1) return vals[0];

    int[] dp = new int[n];
    dp[0] = vals[0];
    dp[1] = Math.max(vals[0], vals[1]);

    for (int i = 2; i < n; i++) {
        dp[i] = Math.max(dp[i - 1], dp[i - 2] + vals[i]);
    }

    return dp[n - 1];
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

int maximumLootWithoutAlertingSecurity(int* vals, int n) {
    if (n == 0) return 0;
    if (n == 1) return vals[0];

    int dp[n];
    dp[0] = vals[0];
    dp[1] = vals[0] > vals[1] ? vals[0] : vals[1];

    for (int i = 2; i < n; i++) {
        int a = dp[i - 1];
        int b = dp[i - 2] + vals[i];
        dp[i] = a > b ? a : b;
    }

    return dp[n - 1];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function maximumLootWithoutAlertingSecurity(vals) {
  const n = vals.length;
  if (n === 0) return 0;
  if (n === 1) return vals[0];

  const dp = Array(n).fill(0);
  dp[0] = vals[0];
  dp[1] = Math.max(vals[0], vals[1]);

  for (let i = 2; i < n; i++) {
    dp[i] = Math.max(dp[i - 1], dp[i - 2] + vals[i]);
  }

  return dp[n - 1];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def maximum_loot_without_alerting_security(vals):
    n = len(vals)
    if n == 0:
        return 0
    if n == 1:
        return vals[0]

    dp = [0] * n
    dp[0] = vals[0]
    dp[1] = max(vals[0], vals[1])

    for i in range(2, n):
        dp[i] = max(dp[i-1], dp[i-2] + vals[i])

    return dp[n-1]

### METADATA

TimeLimit  
1000

MemoryLimit  
512
