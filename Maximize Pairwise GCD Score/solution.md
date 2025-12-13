## CPP

### SOLUTION

int dp[8][1<<14];

int solve(vector<int>& nums, int op, int mask) {
    int n = nums.size();
    int totalOps = n / 2;

    if (op > totalOps) return 0;
    if (dp[op][mask] != -1) return dp[op][mask];

    int best = 0;

    for (int i = 0; i < n; i++) {
        if (mask & (1<<i)) continue;
        for (int j = i+1; j < n; j++) {
            if (mask & (1<<j)) continue;

            int newMask = mask | (1<<i) | (1<<j);
            best = max(best, op * __gcd(nums[i], nums[j]) + solve(nums, op+1, newMask));
        }
    }
    return dp[op][mask] = best;
}

long long maxGCDScore(vector<int>& nums) {
    memset(dp, -1, sizeof(dp));
    return solve(nums, 1, 0);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

static int[][] dp = new int[8][1<<14];

static int gcd(int a, int b) {
    while (b != 0) {
        int t = a % b;
        a = b;
        b = t;
    }
    return a;
}

static int solve(int[] nums, int op, int mask) {
    int n = nums.length;
    int totalOps = n / 2;

    if (op > totalOps) return 0;
    if (dp[op][mask] != -1) return dp[op][mask];

    int best = 0;

    for (int i = 0; i < n; i++) {
        if ((mask & (1<<i)) != 0) continue;
        for (int j = i+1; j < n; j++) {
            if ((mask & (1<<j)) != 0) continue;

            int newMask = mask | (1<<i) | (1<<j);
            best = Math.max(best, op * gcd(nums[i], nums[j]) + solve(nums, op+1, newMask));
        }
    }

    return dp[op][mask] = best;
}

public static long maxGCDScore(int[] nums) {
    for (int i = 0; i < 8; i++)
        Arrays.fill(dp[i], -1);
    return solve(nums, 1, 0);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int dp_c[8][1<<14];

int gcd_c(int a, int b) {
    while (b) {
        int t = a % b;
        a = b;
        b = t;
    }
    return a;
}

int solve_c(int nums[], int n, int op, int mask) {
    int totalOps = n / 2;

    if (op > totalOps) return 0;
    if (dp_c[op][mask] != -1) return dp_c[op][mask];

    int best = 0;

    for (int i = 0; i < n; i++) {
        if (mask & (1<<i)) continue;
        for (int j = i+1; j < n; j++) {
            if (mask & (1<<j)) continue;

            int newMask = mask | (1<<i) | (1<<j);
            int score = op * gcd_c(nums[i], nums[j]) + solve_c(nums, n, op+1, newMask);
            if (score > best) best = score;
        }
    }

    return dp_c[op][mask] = best;
}

long long maxGCDScore(int nums[], int n) {
    for (int i = 0; i < 8; i++)
        for (int j = 0; j < (1<<14); j++)
            dp_c[i][j] = -1;

    return solve_c(nums, n, 1, 0);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function gcd(a, b) {
  while (b !== 0) {
    let t = a % b;
    a = b;
    b = t;
  }
  return a;
}

const dp_js = Array.from({ length: 8 }, () => new Map());

function solveJS(nums, op, mask) {
  const n = nums.length;
  const totalOps = n / 2;

  if (op > totalOps) return 0;
  if (dp_js[op].has(mask)) return dp_js[op].get(mask);

  let best = 0;

  for (let i = 0; i < n; i++) {
    if (mask & (1 << i)) continue;
    for (let j = i + 1; j < n; j++) {
      if (mask & (1 << j)) continue;

      let newMask = mask | (1 << i) | (1 << j);
      let score = op * gcd(nums[i], nums[j]) + solveJS(nums, op + 1, newMask);
      best = Math.max(best, score);
    }
  }

  dp_js[op].set(mask, best);
  return best;
}

function maxGCDScore(nums) {
  for (let i = 0; i < 8; i++) dp_js[i].clear();
  return solveJS(nums, 1, 0);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

from functools import lru_cache
from math import gcd

def maxGCDScore(nums):

    n = len(nums)
    total_ops = n // 2

    @lru_cache(None)
    def solve(op, mask):
        if op > total_ops:
            return 0

        best = 0
        for i in range(n):
            if mask & (1 << i):
                continue
            for j in range(i+1, n):
                if mask & (1 << j):
                    continue

                new_mask = mask | (1 << i) | (1 << j)
                score = op * gcd(nums[i], nums[j]) + solve(op+1, new_mask)
                best = max(best, score)

        return best

    return solve(1, 0)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
