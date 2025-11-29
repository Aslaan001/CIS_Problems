## CPP

### SOLUTION

long long minRemainingSum(vector<long long>& nums, int n, int k) {
    long long sum = 0;
    vector<long long> dp(k, (long long)1e18);
    dp[0] = 0;

    long long prefix = 0;

    for (auto x : nums) {
        prefix += x;
        int idx = prefix % k;
        long long best = dp[idx];
        if (best < prefix) prefix = best;
        dp[idx] = min(dp[idx], prefix);
    }

    return prefix;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## JAVA

### SOLUTION

public static long minRemainingSum(long[] nums, int n, int k) {
    long[] dp = new long[k];
    Arrays.fill(dp, (long)1e18);
    dp[0] = 0;

    long prefix = 0;

    for (long x : nums) {
        prefix += x;
        int idx = (int)(prefix % k);

        long best = dp[idx];
        if (best < prefix) prefix = best;

        dp[idx] = Math.min(dp[idx], prefix);
    }

    return prefix;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## C

### SOLUTION

long long minRemainingSum(long long* nums, int n, int k) {
    long long dp[k];
    for (int i = 0; i < k; i++) dp[i] = (long long)1e18;
    dp[0] = 0;

    long long prefix = 0;

    for (int i = 0; i < n; i++) {
        prefix += nums[i];
        int idx = prefix % k;

        long long best = dp[idx];
        if (best < prefix) prefix = best;

        if (prefix < dp[idx]) dp[idx] = prefix;
    }

    return prefix;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## JAVASCRIPT

### SOLUTION

function minRemainingSum(nums, n, k) {
  const dp = new Array(k).fill(1e18);
  dp[0] = 0;

  let prefix = 0;

  for (let x of nums) {
    prefix += x;
    const idx = prefix % k;

    const best = dp[idx];
    if (best < prefix) prefix = best;

    dp[idx] = Math.min(dp[idx], prefix);
  }

  return prefix;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## PYTHON

### SOLUTION

def min_remaining_sum(nums, n, k):
    dp = [10**30] * k
    dp[0] = 0

    prefix = 0

    for x in nums:
        prefix += x
        idx = prefix % k

        best = dp[idx]
        if best < prefix:
            prefix = best

        if prefix < dp[idx]:
            dp[idx] = prefix

    return prefix

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
