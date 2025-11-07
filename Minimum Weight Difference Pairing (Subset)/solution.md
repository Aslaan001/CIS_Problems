## CPP

### SOLUTION

int minRemainingWeight(vector<int>& nums) {
    int total = 0;
    for (int x : nums) total += x;

    int target = total / 2;
    vector<int> dp(target + 1, 0);

    for (int x : nums) {
        for (int s = target; s >= x; s--) {
            dp[s] = max(dp[s], dp[s - x] + x);
        }
    }
    return total - 2 * dp[target];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int minRemainingWeight(int[] nums) {
    int total = 0;
    for (int x : nums) total += x;

    int target = total / 2;
    int[] dp = new int[target + 1];

    for (int x : nums) {
        for (int s = target; s >= x; s--) {
            dp[s] = Math.max(dp[s], dp[s - x] + x);
        }
    }
    return total - 2 * dp[target];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

int minRemainingWeight(int nums[], int n) {
    int total = 0;
    for (int i = 0; i < n; i++) total += nums[i];

    int target = total / 2;
    int dp[target + 1];
    memset(dp, 0, sizeof(dp));

    for (int i = 0; i < n; i++) {
        for (int s = target; s >= nums[i]; s--) {
            if (dp[s] < dp[s - nums[i]] + nums[i]) {
                dp[s] = dp[s - nums[i]] + nums[i];
            }
        }
    }
    return total - 2 * dp[target];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function minRemainingWeight(nums) {
  let total = nums.reduce((a, b) => a + b, 0);
  let target = Math.floor(total / 2);
  let dp = new Array(target + 1).fill(0);

  for (let x of nums) {
    for (let s = target; s >= x; s--) {
      dp[s] = Math.max(dp[s], dp[s - x] + x);
    }
  }
  return total - 2 * dp[target];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def min_remaining_weight(nums):
    total = sum(nums)
    target = total // 2
    dp = [0] * (target + 1)

    for x in nums:
        for s in range(target, x - 1, -1):
            dp[s] = max(dp[s], dp[s - x] + x)

    return total - 2 * dp[target]

### METADATA

TimeLimit  
1000

MemoryLimit  
512
