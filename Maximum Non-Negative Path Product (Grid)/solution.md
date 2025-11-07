## CPP

### SOLUTION

long long maxNonNegativeProduct(vector<vector<int>>& grid) {
    const long long MOD = 1000000007;
    int m = grid.size(), n = grid[0].size();
    vector<vector<long long>> mx(m, vector<long long>(n));
    vector<vector<long long>> mn(m, vector<long long>(n));
    mx[0][0] = mn[0][0] = grid[0][0];

    for (int i = 1; i < m; i++) {
        mx[i][0] = mn[i][0] = mx[i-1][0] * grid[i][0];
    }
    for (int j = 1; j < n; j++) {
        mx[0][j] = mn[0][j] = mx[0][j-1] * grid[0][j];
    }

    for (int i = 1; i < m; i++) {
        for (int j = 1; j < n; j++) {
            long long a = mx[i-1][j] * grid[i][j];
            long long b = mn[i-1][j] * grid[i][j];
            long long c = mx[i][j-1] * grid[i][j];
            long long d = mn[i][j-1] * grid[i][j];
            mx[i][j] = max(max(a,b), max(c,d));
            mn[i][j] = min(min(a,b), min(c,d));
        }
    }
    if (mx[m-1][n-1] < 0) return -1;
    return mx[m-1][n-1] % MOD;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static long maxNonNegativeProduct(int[][] grid) {
    long MOD = 1000000007;
    int m = grid.length, n = grid[0].length;
    long[][] mx = new long[m][n];
    long[][] mn = new long[m][n];
    mx[0][0] = mn[0][0] = grid[0][0];

    for (int i = 1; i < m; i++) {
        mx[i][0] = mn[i][0] = mx[i-1][0] * grid[i][0];
    }
    for (int j = 1; j < n; j++) {
        mx[0][j] = mn[0][j] = mx[0][j-1] * grid[0][j];
    }

    for (int i = 1; i < m; i++) {
        for (int j = 1; j < n; j++) {
            long a = mx[i-1][j] * grid[i][j];
            long b = mn[i-1][j] * grid[i][j];
            long c = mx[i][j-1] * grid[i][j];
            long d = mn[i][j-1] * grid[i][j];
            mx[i][j] = Math.max(Math.max(a,b), Math.max(c,d));
            mn[i][j] = Math.min(Math.min(a,b), Math.min(c,d));
        }
    }
    if (mx[m-1][n-1] < 0) return -1;
    return mx[m-1][n-1] % MOD;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

long long maxNonNegativeProduct(int grid[][15], int m, int n) {
    long long MOD = 1000000007;
    long long mx[15][15], mn[15][15];
    mx[0][0] = mn[0][0] = grid[0][0];

    for (int i = 1; i < m; i++) {
        mx[i][0] = mn[i][0] = mx[i-1][0] * grid[i][0];
    }
    for (int j = 1; j < n; j++) {
        mx[0][j] = mn[0][j] = mx[0][j-1] * grid[0][j];
    }

    for (int i = 1; i < m; i++) {
        for (int j = 1; j < n; j++) {
            long long a = mx[i-1][j] * grid[i][j];
            long long b = mn[i-1][j] * grid[i][j];
            long long c = mx[i][j-1] * grid[i][j];
            long long d = mn[i][j-1] * grid[i][j];
            long long maxv = a;
            if (b > maxv) maxv = b;
            if (c > maxv) maxv = c;
            if (d > maxv) maxv = d;
            long long minv = a;
            if (b < minv) minv = b;
            if (c < minv) minv = c;
            if (d < minv) minv = d;
            mx[i][j] = maxv;
            mn[i][j] = minv;
        }
    }
    if (mx[m-1][n-1] < 0) return -1;
    return mx[m-1][n-1] % MOD;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function maxNonNegativeProduct(grid) {
  const MOD = 1000000007n;
  const m = grid.length, n = grid[0].length;
  const mx = Array.from({ length: m }, () => Array(n).fill(0n));
  const mn = Array.from({ length: m }, () => Array(n).fill(0n));
  mx[0][0] = mn[0][0] = BigInt(grid[0][0]);

  for (let i = 1; i < m; i++) mx[i][0] = mn[i][0] = mx[i-1][0] * BigInt(grid[i][0]);
  for (let j = 1; j < n; j++) mx[0][j] = mn[0][j] = mx[0][j-1] * BigInt(grid[0][j]);

  for (let i = 1; i < m; i++) {
    for (let j = 1; j < n; j++) {
      let a = mx[i-1][j] * BigInt(grid[i][j]);
      let b = mn[i-1][j] * BigInt(grid[i][j]);
      let c = mx[i][j-1] * BigInt(grid[i][j]);
      let d = mn[i][j-1] * BigInt(grid[i][j]);
      mx[i][j] = a > b ? (a > c ? (a > d ? a : d) : (c > d ? c : d)) : (b > c ? (b > d ? b : d) : (c > d ? c : d));
      mn[i][j] = a < b ? (a < c ? (a < d ? a : d) : (c < d ? c : d)) : (b < c ? (b < d ? b : d) : (c < d ? c : d));
    }
  }
  return mx[m-1][n-1] < 0n ? -1 : Number(mx[m-1][n-1] % MOD);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def max_non_negative_product(grid):
    MOD = 1000000007
    m, n = len(grid), len(grid[0])
    mx = [[0]*n for _ in range(m)]
    mn = [[0]*n for _ in range(m)]
    mx[0][0] = mn[0][0] = grid[0][0]

    for i in range(1, m):
        val = mx[i-1][0] * grid[i][0]
        mx[i][0] = mn[i][0] = val
    for j in range(1, n):
        val = mx[0][j-1] * grid[0][j]
        mx[0][j] = mn[0][j] = val

    for i in range(1, m):
        for j in range(1, n):
            values = [
                mx[i-1][j] * grid[i][j],
                mn[i-1][j] * grid[i][j],
                mx[i][j-1] * grid[i][j],
                mn[i][j-1] * grid[i][j]
            ]
            mx[i][j] = max(values)
            mn[i][j] = min(values)

    if mx[m-1][n-1] < 0:
        return -1
    return mx[m-1][n-1] % MOD

### METADATA

TimeLimit  
1000

MemoryLimit  
512
