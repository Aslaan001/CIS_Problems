## CPP

### SOLUTION

int maxTriDivisibleSum(vector<int>& nums) {
    long long dp[3] = {0, LLONG_MIN/2, LLONG_MIN/2};
    for (int x : nums) {
        long long ndp[3];
        for (int i = 0; i < 3; i++) ndp[i] = dp[i];
        for (int i = 0; i < 3; i++) {
            int mod = (i + x % 3 + 3) % 3;
            ndp[mod] = max(ndp[mod], dp[i] + x);
        }
        for (int i = 0; i < 3; i++) dp[i] = ndp[i];
    }
    return dp[0];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVA

### SOLUTION

public static int maxTriDivisibleSum(int[] nums) {
    long[] dp = {0, Long.MIN_VALUE/2, Long.MIN_VALUE/2};
    for (int x : nums) {
        long[] ndp = dp.clone();
        int xm = x % 3;
        for (int i = 0; i < 3; i++) {
            int mod = (i + xm + 3) % 3;
            ndp[mod] = Math.max(ndp[mod], dp[i] + x);
        }
        dp = ndp;
    }
    return (int) dp[0];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## C

### SOLUTION

long long maxTriDivisibleSum(int* nums, int n) {
    long long dp[3] = {0, LLONG_MIN/2, LLONG_MIN/2};
    for (int i = 0; i < n; i++) {
        int x = nums[i];
        long long ndp[3];
        for (int j = 0; j < 3; j++) ndp[j] = dp[j];
        for (int j = 0; j < 3; j++) {
            int mod = (j + (x % 3) + 3) % 3;
            if (dp[j] + x > ndp[mod]) ndp[mod] = dp[j] + x;
        }
        for (int j = 0; j < 3; j++) dp[j] = ndp[j];
    }
    return dp[0];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION

function maxTriDivisibleSum(nums) {
  let dp = [0n, -10n**18n, -10n**18n];
  for (let x of nums) {
    x = BigInt(x);
    let ndp = [...dp];
    let xm = Number(x % 3n);
    for (let i = 0; i < 3; i++) {
      const mod = (i + xm) % 3;
      const val = dp[i] + x;
      if (val > ndp[mod]) ndp[mod] = val;
    }
    dp = ndp;
  }
  return Number(dp[0]);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def max_tri_divisible_sum(nums):
    dp = [0, -10**30, -10**30]
    for x in nums:
        ndp = dp[:]
        xm = x % 3
        for i in range(3):
            mod = (i + xm) % 3
            ndp[mod] = max(ndp[mod], dp[i] + x)
        dp = ndp
    return dp[0]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512