## CPP

bool predictWinner(vector<int>& nums) {
    int n = nums.size();
    vector<vector<int>> dp(n, vector<int>(n, 0));

    for (int i = 0; i < n; i++) dp[i][i] = nums[i];

    for (int len = 2; len <= n; len++) {
        for (int l = 0; l + len - 1 < n; l++) {
            int r = l + len - 1;
            dp[l][r] = max(
                nums[l] - dp[l + 1][r],
                nums[r] - dp[l][r - 1]
            );
        }
    }
    return dp[0][n - 1] >= 0;
}


## JAVA

public static boolean predictWinner(int[] nums) {
    int n = nums.length;
    int[][] dp = new int[n][n];

    for (int i = 0; i < n; i++)
        dp[i][i] = nums[i];

    for (int len = 2; len <= n; len++) {
        for (int l = 0; l + len - 1 < n; l++) {
            int r = l + len - 1;
            dp[l][r] = Math.max(
                nums[l] - dp[l + 1][r],
                nums[r] - dp[l][r - 1]
            );
        }
    }
    return dp[0][n - 1] >= 0;
}


## C

#include <stdbool.h>

bool predictWinner(int* nums, int numsSize) {
    int dp[25][25] = {0};

    for (int i = 0; i < numsSize; i++)
        dp[i][i] = nums[i];

    for (int len = 2; len <= numsSize; len++) {
        for (int l = 0; l + len - 1 < numsSize; l++) {
            int r = l + len - 1;
            int takeL = nums[l] - dp[l + 1][r];
            int takeR = nums[r] - dp[l][r - 1];
            dp[l][r] = takeL > takeR ? takeL : takeR;
        }
    }
    return dp[0][numsSize - 1] >= 0;
}


## JAVASCRIPT

function predictWinner(nums) {
    const n = nums.length;
    const dp = Array.from({ length: n }, () => Array(n).fill(0));

    for (let i = 0; i < n; i++) dp[i][i] = nums[i];

    for (let len = 2; len <= n; len++) {
        for (let l = 0; l + len - 1 < n; l++) {
            const r = l + len - 1;
            dp[l][r] = Math.max(
                nums[l] - dp[l + 1][r],
                nums[r] - dp[l][r - 1]
            );
        }
    }
    return dp[0][n - 1] >= 0;
}


## PYTHON

def predict_winner(nums):
    n = len(nums)
    dp = [[0]*n for _ in range(n)]

    for i in range(n):
        dp[i][i] = nums[i]

    for length in range(2, n + 1):
        for l in range(n - length + 1):
            r = l + length - 1
            dp[l][r] = max(
                nums[l] - dp[l + 1][r],
                nums[r] - dp[l][r - 1]
            )

    return dp[0][n - 1] >= 0
