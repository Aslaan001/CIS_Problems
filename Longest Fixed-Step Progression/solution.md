## CPP

### SOLUTION

int longestFixedStepProgression(vector<int>& nums, int step) {
    unordered_map<int,int> dp;
    int ans = 1;
    for (int x : nums) {
        int prev = x - step;
        dp[x] = dp.count(prev) ? dp[prev] + 1 : 1;
        ans = max(ans, dp[x]);
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

public static int longestFixedStepProgression(int[] nums, int step) {
    HashMap<Integer, Integer> dp = new HashMap<>();
    int ans = 1;
    for (int x : nums) {
        int prev = x - step;
        int val = dp.getOrDefault(prev, 0) + 1;
        dp.put(x, val);
        ans = Math.max(ans, val);
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

int longestFixedStepProgression(int nums[], int n, int step) {
    int dp[200001];
    for (int i = 0; i < 200001; i++) dp[i] = 0;
    int offset = 100000;
    int ans = 1;
    for (int i = 0; i < n; i++) {
        int x = nums[i] + offset;
        int prev = nums[i] - step + offset;
        int val = 1;
        if (prev >= 0 && prev < 200001) {
            val = dp[prev] + 1;
        }
        dp[x] = val;
        if (val > ans) ans = val;
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

function longestFixedStepProgression(nums, step) {
  const dp = new Map();
  let ans = 1;
  for (const x of nums) {
    const prev = x - step;
    const val = (dp.get(prev) || 0) + 1;
    dp.set(x, val);
    ans = Math.max(ans, val);
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

def longest_fixed_step_progression(nums, step):
    dp = {}
    ans = 1
    for x in nums:
        prev = x - step
        dp[x] = dp.get(prev, 0) + 1
        ans = max(ans, dp[x])
    return ans

### METADATA

TimeLimit  
1000  

MemoryLimit  
512
