## CPP

### SOLUTION

long long minXorSum(vector<int>& nums1, vector<int>& nums2) {
    int n = nums1.size();

    vector<vector<int>> cost(n, vector<int>(n));
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            cost[i][j] = nums1[i] ^ nums2[j];

    int full = (1 << n) - 1;
    vector<long long> dp(1 << n, -1);

    function<long long(int,int)> solve = [&](int r, int mask) {
        if (r >= n) return 0LL;
        if (dp[mask] != -1) return dp[mask];

        long long ans = LLONG_MAX;

        for (int j = 0; j < n; j++) {
            if (mask & (1 << j)) {
                long long v = cost[r][j] + solve(r + 1, mask ^ (1 << j));
                ans = min(ans, v);
            }
        }
        return dp[mask] = ans;
    };

    return solve(0, full);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static long minXorSum(int[] nums1, int[] nums2) {
    int n = nums1.length;
    long[][] cost = new long[n][n];

    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            cost[i][j] = nums1[i] ^ nums2[j];

    int full = (1 << n) - 1;
    long[] dp = new long[1 << n];
    Arrays.fill(dp, -1);

    return solveMin(0, full, cost, dp, n);
}

private static long solveMin(int r, int mask, long[][] cost, long[] dp, int n) {
    if (r >= n) return 0;
    if (dp[mask] != -1) return dp[mask];

    long ans = Long.MAX_VALUE;

    for (int j = 0; j < n; j++) {
        if ((mask & (1 << j)) != 0) {
            long v = cost[r][j] + solveMin(r+1, mask ^ (1<<j), cost, dp, n);
            if (v < ans) ans = v;
        }
    }

    return dp[mask] = ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

long long solveMask(int r, int mask, long long** cost, long long dp[], int n) {
    if (r >= n) return 0;
    if (dp[mask] != -1) return dp[mask];

    long long ans = LLONG_MAX;

    for (int j = 0; j < n; j++) {
        if (mask & (1 << j)) {
            long long v = cost[r][j] + solveMask(r+1, mask ^ (1<<j), cost, dp, n);
            if (v < ans) ans = v;
        }
    }

    return dp[mask] = ans;
}

long long minXorSum(int nums1[], int nums2[], int n) {
    long long** cost = malloc(n * sizeof(long long*));
    for (int i = 0; i < n; i++) {
        cost[i] = malloc(n * sizeof(long long));
        for (int j = 0; j < n; j++) {
            cost[i][j] = nums1[i] ^ nums2[j];
        }
    }

    int full = (1<<n) - 1;
    long long* dp = malloc((1<<n) * sizeof(long long));
    for (int i = 0; i < (1<<n); i++) dp[i] = -1;

    long long ans = solveMask(0, full, cost, dp, n);

    for (int i = 0; i < n; i++) free(cost[i]);
    free(cost);
    free(dp);

    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function minXorSum(nums1, nums2) {
    const n = nums1.length;

    const cost = Array.from({ length: n }, () => Array(n).fill(0));
    for (let i = 0; i < n; i++)
        for (let j = 0; j < n; j++)
            cost[i][j] = nums1[i] ^ nums2[j];

    const full = (1 << n) - 1;
    const dp = new Map();

    function solve(r, mask) {
        if (r >= n) return 0;
        if (dp.has(mask)) return dp.get(mask);

        let ans = Number.MAX_SAFE_INTEGER;

        for (let j = 0; j < n; j++) {
            if (mask & (1 << j)) {
                const v = cost[r][j] + solve(r + 1, mask ^ (1 << j));
                if (v < ans) ans = v;
            }
        }

        dp.set(mask, ans);
        return ans;
    }

    return solve(0, full);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

from functools import lru_cache

def minXorSum(nums1, nums2):
    n = len(nums1)

    cost = [[nums1[i] ^ nums2[j] for j in range(n)] for i in range(n)]
    full = (1 << n) - 1

    @lru_cache(None)
    def solve(r, mask):
        if r >= n:
            return 0

        best = 10**18
        for j in range(n):
            if mask & (1 << j):
                v = cost[r][j] + solve(r+1, mask ^ (1 << j))
                best = min(best, v)
        return best

    return solve(0, full)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
