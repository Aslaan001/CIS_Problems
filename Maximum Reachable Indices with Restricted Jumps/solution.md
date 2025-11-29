## CPP

### SOLUTION

int memo_arr[1005];

int dfs_jump(vector<int>& arr, int index, int d) {
    if (memo_arr[index] != -1)
        return memo_arr[index];

    memo_arr[index] = 0;

    for (int i = index + 1; i < arr.size() && arr[i] < arr[index] && i <= index + d; i++)
        memo_arr[index] = max(memo_arr[index], 1 + dfs_jump(arr, i, d));

    for (int i = index - 1; i >= 0 && arr[i] < arr[index] && i >= index - d; i--)
        memo_arr[index] = max(memo_arr[index], 1 + dfs_jump(arr, i, d));

    return memo_arr[index];
}

int maxIndicesVisited(vector<int>& nums, int d) {
    memset(memo_arr, -1, sizeof memo_arr);
    int ans = 0;
    for (int i = 0; i < nums.size(); i++)
        ans = max(ans, 1 + dfs_jump(nums, i, d));
    return ans;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

static int[] memo_arr;

public static int dfs(int[] arr, int index, int d) {
    if (memo_arr[index] != -1)
        return memo_arr[index];

    memo_arr[index] = 0;

    for (int i = index + 1; i < arr.length && arr[i] < arr[index] && i <= index + d; i++)
        memo_arr[index] = Math.max(memo_arr[index], 1 + dfs(arr, i, d));

    for (int i = index - 1; i >= 0 && arr[i] < arr[index] && i >= index - d; i--)
        memo_arr[index] = Math.max(memo_arr[index], 1 + dfs(arr, i, d));

    return memo_arr[index];
}

public static int maxIndicesVisited(int[] nums, int d) {
    memo_arr = new int[nums.length];
    Arrays.fill(memo_arr, -1);

    int ans = 0;
    for (int i = 0; i < nums.length; i++)
        ans = Math.max(ans, 1 + dfs(nums, i, d));
    return ans;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## C

### SOLUTION

int memo_arr[1005];

int dfs_jump(int* arr, int n, int index, int d) {
    if (memo_arr[index] != -1)
        return memo_arr[index];

    memo_arr[index] = 0;

    for (int i = index + 1; i < n && arr[i] < arr[index] && i <= index + d; i++) {
        int val = 1 + dfs_jump(arr, n, i, d);
        if (val > memo_arr[index]) memo_arr[index] = val;
    }

    for (int i = index - 1; i >= 0 && arr[i] < arr[index] && i >= index - d; i--) {
        int val = 1 + dfs_jump(arr, n, i, d);
        if (val > memo_arr[index]) memo_arr[index] = val;
    }

    return memo_arr[index];
}

int maxIndicesVisited(int* nums, int n, int d) {
    for (int i = 0; i < 1005; i++) memo_arr[i] = -1;

    int ans = 0;
    for (int i = 0; i < n; i++) {
        int val = 1 + dfs_jump(nums, n, i, d);
        if (val > ans) ans = val;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function maxIndicesVisited(nums, d) {
  const n = nums.length;
  const memo = new Array(n).fill(-1);

  function dfs(i) {
    if (memo[i] !== -1) return memo[i];

    memo[i] = 0;

    for (let j = i + 1; j < n && nums[j] < nums[i] && j <= i + d; j++)
      memo[i] = Math.max(memo[i], 1 + dfs(j));

    for (let j = i - 1; j >= 0 && nums[j] < nums[i] && j >= i - d; j--)
      memo[i] = Math.max(memo[i], 1 + dfs(j));

    return memo[i];
  }

  let ans = 0;
  for (let i = 0; i < n; i++)
    ans = Math.max(ans, 1 + dfs(i));

  return ans;
}


### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def max_indices_visited(nums, d):
    n = len(nums)
    memo = [-1] * n

    def dfs(i):
        if memo[i] != -1:
            return memo[i]

        memo[i] = 0

        for j in range(i + 1, min(n, i + d + 1)):
            if nums[j] >= nums[i]:
                break
            memo[i] = max(memo[i], 1 + dfs(j))

        for j in range(i - 1, max(-1, i - d) - 1, -1):
            if nums[j] >= nums[i]:
                break
            memo[i] = max(memo[i], 1 + dfs(j))

        return memo[i]

    ans = 0
    for i in range(n):
        ans = max(ans, 1 + dfs(i))

    return ans

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512
