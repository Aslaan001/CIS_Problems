## CPP

### SOLUTION

int minRemainingStone(vector<int>& nums) {
    int total = 0;
    for (int x : nums) total += x;
    int n = nums.size();
    vector<vector<int>> dp(n + 1, vector<int>(total + 1, -1));

    function<int(int,int)> f = [&](int i, int path) {
        if (i >= n) return 0;
        if (dp[i][path] != -1) return dp[i][path];

        int skip = f(i + 1, path);
        int take = 0;
        if (2 * (path + nums[i]) <= total) {
            take = nums[i] + f(i + 1, path + nums[i]);
        }
        return dp[i][path] = max(skip, take);
    };

    int half = f(0, 0);
    return total - 2 * half;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int minRemainingStone(int[] nums) {
    int total = 0;
    for (int x : nums) total += x;
    int n = nums.length;

    int[][] dp = new int[n + 1][total + 1];
    for (int i = 0; i <= n; i++)
        Arrays.fill(dp[i], -1);

    return total - 2 * dfs(0, 0, nums, total, dp);
}

private static int dfs(int i, int path, int[] nums, int total, int[][] dp) {
    if (i >= nums.length) return 0;
    if (dp[i][path] != -1) return dp[i][path];

    int skip = dfs(i + 1, path, nums, total, dp);
    int take = 0;
    if (2 * (path + nums[i]) <= total) {
        take = nums[i] + dfs(i + 1, path + nums[i], nums, total, dp);
    }
    return dp[i][path] = Math.max(skip, take);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int minRemainingStone(int* nums, int n) {
    int total = 0;
    for (int i = 0; i < n; i++) total += nums[i];

    int dp[n + 1][total + 1];
    for (int i = 0; i <= n; i++)
        for (int j = 0; j <= total; j++)
            dp[i][j] = -1;

    int (*f)(int,int) = NULL;

    int dfs(int i, int path) {
        if (i >= n) return 0;
        if (dp[i][path] != -1) return dp[i][path];

        int skip = dfs(i + 1, path);
        int take = 0;
        if (2 * (path + nums[i]) <= total) {
            take = nums[i] + dfs(i + 1, path + nums[i]);
        }
        dp[i][path] = skip > take ? skip : take;
        return dp[i][path];
    }

    // assign function pointer
    f = dfs;

    int half = f(0, 0);
    return total - 2 * half;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function minRemainingStone(nums) {
  const n = nums.length;
  let total = 0;
  for (const x of nums) total += x;

  const dp = Array.from({ length: n + 1 }, () =>
    new Array(total + 1).fill(-1)
  );

  function dfs(i, path) {
    if (i >= n) return 0;
    if (dp[i][path] !== -1) return dp[i][path];

    const skip = dfs(i + 1, path);
    let take = 0;

    if (2 * (path + nums[i]) <= total) {
      take = nums[i] + dfs(i + 1, path + nums[i]);
    }

    return (dp[i][path] = Math.max(skip, take));
  }

  const half = dfs(0, 0);
  return total - 2 * half;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def min_remaining_stone(nums):
    total = sum(nums)
    n = len(nums)
    dp = [[-1] * (total + 1) for _ in range(n + 1)]

    def dfs(i, path):
        if i >= n:
            return 0
        if dp[i][path] != -1:
            return dp[i][path]

        skip = dfs(i + 1, path)
        take = 0
        if 2 * (path + nums[i]) <= total:
            take = nums[i] + dfs(i + 1, path + nums[i])

        dp[i][path] = max(skip, take)
        return dp[i][path]

    half = dfs(0, 0)
    return total - 2 * half

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
