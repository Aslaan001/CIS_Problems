## CPP

### SOLUTION

int dp[1001][1001], n;

int findMinCost(vector<int>& nums, int prevElementIndex, int curIndex) {
    if (curIndex == n) return nums[prevElementIndex];
    else if (curIndex == n - 1) return max(nums[prevElementIndex], nums[curIndex]);

    if (dp[prevElementIndex][curIndex] != -1) return dp[prevElementIndex][curIndex];

    int cost = INT_MAX;

    cost = max(nums[curIndex], nums[curIndex + 1]) + findMinCost(nums, prevElementIndex, curIndex + 2);
    cost = min(cost, max(nums[prevElementIndex], nums[curIndex + 1]) + findMinCost(nums, curIndex, curIndex + 2));
    cost = min(cost, max(nums[prevElementIndex], nums[curIndex]) + findMinCost(nums, curIndex + 1, curIndex + 2));

    return dp[prevElementIndex][curIndex] = cost;
}

int controlledPairRemovalCost(vector<int>& nums) {
    n = nums.size();
    memset(dp, -1, sizeof(dp));
    return findMinCost(nums, 0, 1);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int controlledPairRemovalCost(int[] nums) {
    int n = nums.length;
    int[][] dp = new int[n][n];
    for (int i = 0; i < n; i++) {
        Arrays.fill(dp[i], -1);
    }

    java.util.function.BiFunction<Integer, Integer, Integer> solve = new java.util.function.BiFunction<>() {
        @Override
        public Integer apply(Integer prev, Integer cur) {
            if (cur == n) return nums[prev];
            if (cur == n - 1) return Math.max(nums[prev], nums[cur]);
            if (dp[prev][cur] != -1) return dp[prev][cur];

            int cost = Integer.MAX_VALUE;

            cost = Math.max(nums[cur], nums[cur + 1]) + apply(prev, cur + 2);
            cost = Math.min(cost, Math.max(nums[prev], nums[cur + 1]) + apply(cur, cur + 2));
            cost = Math.min(cost, Math.max(nums[prev], nums[cur]) + apply(cur + 1, cur + 2));

            return dp[prev][cur] = cost;
        }
    };

    return solve.apply(0, 1);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

int dp[1001][1001], n;

int findMinCost(int nums[], int prev, int cur) {
    if (cur == n) return nums[prev];
    else if (cur == n - 1) return nums[prev] > nums[cur] ? nums[prev] : nums[cur];

    if (dp[prev][cur] != -1) return dp[prev][cur];

    int cost = 2147483647;

    int c1 = (nums[cur] > nums[cur+1] ? nums[cur] : nums[cur+1]) + findMinCost(nums, prev, cur+2);
    if (c1 < cost) cost = c1;

    int c2 = (nums[prev] > nums[cur+1] ? nums[prev] : nums[cur+1]) + findMinCost(nums, cur, cur+2);
    if (c2 < cost) cost = c2;

    int c3 = (nums[prev] > nums[cur] ? nums[prev] : nums[cur]) + findMinCost(nums, cur+1, cur+2);
    if (c3 < cost) cost = c3;

    return dp[prev][cur] = cost;
}

int controlledPairRemovalCost(int nums[], int size) {
    n = size;
    memset(dp, -1, sizeof(dp));
    return findMinCost(nums, 0, 1);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function controlledPairRemovalCost(nums) {
    const n = nums.length;
    const dp = Array.from({ length: n }, () => Array(n).fill(-1));

    function solve(prev, cur) {
        if (cur === n) return nums[prev];
        if (cur === n - 1) return Math.max(nums[prev], nums[cur]);
        if (dp[prev][cur] !== -1) return dp[prev][cur];

        let cost = Infinity;

        cost = Math.max(nums[cur], nums[cur + 1]) + solve(prev, cur + 2);
        cost = Math.min(cost, Math.max(nums[prev], nums[cur + 1]) + solve(cur, cur + 2));
        cost = Math.min(cost, Math.max(nums[prev], nums[cur]) + solve(cur + 1, cur + 2));

        return dp[prev][cur] = cost;
    }

    return solve(0, 1);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def controlled_pair_removal_cost(nums):
    n = len(nums)
    dp = [[-1] * n for _ in range(n)]

    def solve(prev, cur):
        if cur == n:
            return nums[prev]
        if cur == n - 1:
            return max(nums[prev], nums[cur])
        if dp[prev][cur] != -1:
            return dp[prev][cur]

        cost = float('inf')
        cost = min(cost, max(nums[cur], nums[cur+1]) + solve(prev, cur+2))
        cost = min(cost, max(nums[prev], nums[cur+1]) + solve(cur, cur+2))
        cost = min(cost, max(nums[prev], nums[cur]) + solve(cur+1, cur+2))

        dp[prev][cur] = cost
        return cost

    return solve(0, 1)

### METADATA

TimeLimit  
1000

MemoryLimit  
512
