## CPP

### SOLUTION

int charmingTripleSplits(vector<int>& nums) {
    int n = nums.size();
    if (n < 3) return 0;

    vector<vector<int>> dp(n + 1, vector<int>(n + 1, 0));
    for (int i = n - 1; i >= 0; i--) {
        for (int j = i; j < n; j++) {
            if (nums[i] == nums[j]) dp[i][j] = 1 + dp[i + 1][j + 1];
        }
    }

    int ans = 0;
    for (int i = 0; i < n - 2; i++) {
        for (int j = i + 1; j < n - 1; j++) {
            int len1 = i + 1;
            int len2 = j - i;
            int len3 = n - j;
            if ((dp[0][i + 1] >= len1 && len1 <= len2) || (dp[i + 1][j + 1] >= len2 && len2 <= len3))
                ans++;
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

public static int charmingTripleSplits(int[] nums) {
    int n = nums.length;
    if (n < 3) return 0;

    int[][] dp = new int[n + 1][n + 1];
    for (int i = n - 1; i >= 0; i--) {
        for (int j = i; j < n; j++) {
            if (nums[i] == nums[j]) dp[i][j] = 1 + dp[i + 1][j + 1];
        }
    }

    int ans = 0;
    for (int i = 0; i < n - 2; i++) {
        for (int j = i + 1; j < n - 1; j++) {
            int len1 = i + 1;
            int len2 = j - i;
            int len3 = n - j;
            if ((dp[0][i + 1] >= len1 && len1 <= len2) || (dp[i + 1][j + 1] >= len2 && len2 <= len3))
                ans++;
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

int charmingTripleSplits(int* nums, int n) {
    if (n < 3) return 0;

    int** dp = (int**)malloc((n + 1) * sizeof(int*));
    for (int i = 0; i <= n; i++) dp[i] = (int*)calloc(n + 1, sizeof(int));

    for (int i = n - 1; i >= 0; i--) {
        for (int j = i; j < n; j++) {
            if (nums[i] == nums[j]) dp[i][j] = 1 + dp[i + 1][j + 1];
        }
    }

    int ans = 0;
    for (int i = 0; i < n - 2; i++) {
        for (int j = i + 1; j < n - 1; j++) {
            int len1 = i + 1;
            int len2 = j - i;
            int len3 = n - j;
            if ((dp[0][i + 1] >= len1 && len1 <= len2) || (dp[i + 1][j + 1] >= len2 && len2 <= len3))
                ans++;
        }
    }

    for (int i = 0; i <= n; i++) free(dp[i]);
    free(dp);
    return ans;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  



## JAVASCRIPT

### SOLUTION

function charmingTripleSplits(nums) {
    const n = nums.length;
    if (n < 3) return 0;

    const dp = Array.from({ length: n + 1 }, () => Array(n + 1).fill(0));

    for (let i = n - 1; i >= 0; i--) {
        for (let j = i; j < n; j++) {
            if (nums[i] === nums[j]) dp[i][j] = 1 + dp[i + 1][j + 1];
        }
    }

    let ans = 0;
    for (let i = 0; i < n - 2; i++) {
        for (let j = i + 1; j < n - 1; j++) {
            const len1 = i + 1;
            const len2 = j - i;
            const len3 = n - j;
            if ((dp[0][i + 1] >= len1 && len1 <= len2) || (dp[i + 1][j + 1] >= len2 && len2 <= len3))
                ans++;
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

def charming_triple_splits(nums):
    n = len(nums)
    if n < 3:
        return 0

    dp = [[0] * (n + 1) for _ in range(n + 1)]
    for i in range(n - 1, -1, -1):
        for j in range(i, n):
            if nums[i] == nums[j]:
                dp[i][j] = 1 + dp[i + 1][j + 1]

    ans = 0
    for i in range(n - 2):
        for j in range(i + 1, n - 1):
            len1 = i + 1
            len2 = j - i
            len3 = n - j
            if (dp[0][i + 1] >= len1 and len1 <= len2) or (dp[i + 1][j + 1] >= len2 and len2 <= len3):
                ans += 1
    return ans

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  
