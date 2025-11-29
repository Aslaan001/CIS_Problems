## CPP

### SOLUTION

int maxPartitionSum(vector<int>& nums, int k) {
    int n = nums.size();
    vector<int> dp(n + 1, 0);
    for (int i = 1; i <= n; i++) {
        int curMax = 0;
        for (int len = 1; len <= k && i - len >= 0; len++) {
            curMax = max(curMax, nums[i - len]);
            dp[i] = max(dp[i], dp[i - len] + curMax * len);
        }
    }
    return dp[n];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVA

### SOLUTION

public static int maxPartitionSum(int[] nums, int k) {
    int n = nums.length;
    int[] dp = new int[n + 1];
    for (int i = 1; i <= n; i++) {
        int curMax = 0;
        for (int len = 1; len <= k && i - len >= 0; len++) {
            curMax = Math.max(curMax, nums[i - len]);
            dp[i] = Math.max(dp[i], dp[i - len] + curMax * len);
        }
    }
    return dp[n];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## C

### SOLUTION

int maxPartitionSum(int* nums, int n, int k) {
    int dp[n + 1];
    for (int i = 0; i <= n; i++) dp[i] = 0;

    for (int i = 1; i <= n; i++) {
        int curMax = 0;
        for (int len = 1; len <= k && i - len >= 0; len++) {
            if (nums[i - len] > curMax) curMax = nums[i - len];
            int option = dp[i - len] + curMax * len;
            if (option > dp[i]) dp[i] = option;
        }
    }
    return dp[n];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION

function maxPartitionSum(nums, k) {
  const n = nums.length;
  const dp = new Array(n + 1).fill(0);

  for (let i = 1; i <= n; i++) {
    let curMax = 0;
    for (let len = 1; len <= k && i - len >= 0; len++) {
      curMax = Math.max(curMax, nums[i - len]);
      dp[i] = Math.max(dp[i], dp[i - len] + curMax * len);
    }
  }
  return dp[n];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def max_partition_sum(nums, k):
    n = len(nums)
    dp = [0] * (n + 1)
    for i in range(1, n + 1):
        cur_max = 0
        for length in range(1, k + 1):
            if i - length < 0:
                break
            cur_max = max(cur_max, nums[i - length])
            dp[i] = max(dp[i], dp[i - length] + cur_max * length)
    return dp[n]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512