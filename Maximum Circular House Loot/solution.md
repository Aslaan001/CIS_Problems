## CPP

### SOLUTION

int robLine(vector<int>& a) {
    int n = a.size();
    if (n == 0) return 0;
    if (n == 1) return a[0];
    vector<int> dp(n);
    dp[0] = a[0];
    dp[1] = max(a[0], a[1]);
    for (int i = 2; i < n; i++) dp[i] = max(dp[i-1], dp[i-2] + a[i]);
    return dp[n-1];
}

int maximumCircularHouseLoot(vector<int>& vals) {
    int n = vals.size();
    if (n == 1) return vals[0];
    vector<int> a(vals.begin()+1, vals.end());
    vector<int> b(vals.begin(), vals.end()-1);
    return max(robLine(a), robLine(b));
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int maximumCircularHouseLoot(int[] vals) {
    int n = vals.length;
    if (n == 1) return vals[0];

    java.util.function.Function<int[], Integer> robLine = (arr) -> {
        int m = arr.length;
        if (m == 0) return 0;
        if (m == 1) return arr[0];
        int[] dp = new int[m];
        dp[0] = arr[0];
        dp[1] = Math.max(arr[0], arr[1]);
        for (int i = 2; i < m; i++) dp[i] = Math.max(dp[i-1], dp[i-2] + arr[i]);
        return dp[m-1];
    };

    int[] a = java.util.Arrays.copyOfRange(vals, 1, n);
    int[] b = java.util.Arrays.copyOfRange(vals, 0, n-1);

    return Math.max(robLine.apply(a), robLine.apply(b));
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

int robLine(int* arr, int m) {
    if (m == 0) return 0;
    if (m == 1) return arr[0];
    int dp[m];
    dp[0] = arr[0];
    dp[1] = arr[0] > arr[1] ? arr[0] : arr[1];
    for (int i = 2; i < m; i++) {
        int a = dp[i-1];
        int b = dp[i-2] + arr[i];
        dp[i] = a > b ? a : b;
    }
    return dp[m-1];
}

int maximumCircularHouseLoot(int* vals, int n) {
    if (n == 1) return vals[0];
    int a[n-1], b[n-1];
    for (int i = 1; i < n; i++) a[i-1] = vals[i];
    for (int i = 0; i < n-1; i++) b[i] = vals[i];
    int x = robLine(a, n-1);
    int y = robLine(b, n-1);
    return x > y ? x : y;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function maximumCircularHouseLoot(vals) {
  const n = vals.length;
  if (n === 1) return vals[0];

  function robLine(a) {
    const m = a.length;
    if (m === 0) return 0;
    if (m === 1) return a[0];
    const dp = Array(m).fill(0);
    dp[0] = a[0];
    dp[1] = Math.max(a[0], a[1]);
    for (let i = 2; i < m; i++) dp[i] = Math.max(dp[i-1], dp[i-2] + a[i]);
    return dp[m-1];
  }

  const a = vals.slice(1);
  const b = vals.slice(0, n-1);
  return Math.max(robLine(a), robLine(b));
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def maximum_circular_house_loot(vals):
    n = len(vals)
    if n == 1:
        return vals[0]

    def robLine(a):
        m = len(a)
        if m == 0:
            return 0
        if m == 1:
            return a[0]
        dp = [0]*m
        dp[0] = a[0]
        dp[1] = max(a[0], a[1])
        for i in range(2, m):
            dp[i] = max(dp[i-1], dp[i-2] + a[i])
        return dp[m-1]

    a = vals[1:]
    b = vals[:-1]
    return max(robLine(a), robLine(b))

### METADATA

TimeLimit  
1000

MemoryLimit  
512
