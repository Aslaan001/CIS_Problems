## CPP

### SOLUTION

int longestBalancedProgression(vector<int>& nums) {
    int n = nums.size();
    if (n <= 1) return n;
    vector<unordered_map<int,int>> dp(n);
    int ans = 1;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i; j++) {
            int d = nums[i] - nums[j];
            dp[i][d] = (dp[j].count(d) ? dp[j][d] : 1) + 1;
            ans = max(ans, dp[i][d]);
        }
    }
    return ans;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int longestBalancedProgression(int[] nums) {
    int n = nums.length;
    if (n <= 1) return n;
    HashMap<Integer, Integer>[] dp = new HashMap[n];
    for (int i = 0; i < n; i++) dp[i] = new HashMap<>();
    int ans = 1;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i; j++) {
            int d = nums[i] - nums[j];
            int prev = dp[j].getOrDefault(d, 1);
            dp[i].put(d, prev + 1);
            ans = Math.max(ans, prev + 1);
        }
    }
    return ans;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

#include <limits.h>

int longestBalancedProgression(int nums[], int n) {
    if (n <= 1) return n;
    int dp[n][1001];
    memset(dp, 0, sizeof(dp));
    int ans = 1;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < i; j++) {
            int d = nums[i] - nums[j] + 500;
            dp[i][d] = dp[j][d] + 1;
            if (dp[i][d] == 1) dp[i][d] = 2;
            if (dp[i][d] > ans) ans = dp[i][d];
        }
    }
    return ans;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function longestBalancedProgression(nums) {
  const n = nums.length;
  if (n <= 1) return n;
  const dp = Array.from({ length: n }, () => new Map());
  let ans = 1;

  for (let i = 0; i < n; i++) {
    for (let j = 0; j < i; j++) {
      const d = nums[i] - nums[j];
      const prev = dp[j].has(d) ? dp[j].get(d) : 1;
      dp[i].set(d, prev + 1);
      ans = Math.max(ans, prev + 1);
    }
  }
  return ans;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def longest_balanced_progression(nums):
    n = len(nums)
    if n <= 1:
        return n
    dp = [dict() for _ in range(n)]
    ans = 1

    for i in range(n):
        for j in range(i):
            d = nums[i] - nums[j]
            prev = dp[j].get(d, 1)
            dp[i][d] = prev + 1
            ans = max(ans, prev + 1)

    return ans

### METADATA

TimeLimit  
1000

MemoryLimit  
512
