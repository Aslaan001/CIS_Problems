## CPP

### SOLUTION

long long minCostToReachTop(vector<long long>& costs, int n) {
    const long long INF = LLONG_MAX / 4;
    vector<long long> dp(n + 1, INF);
    dp[0] = 0;

    for (int i = 1; i <= n; i++) {
        for (int k = 1; k <= 3; k++) {
            int prev = i - k;
            if (prev < 0) break;
            long long jumpCost = costs[i] + 1LL * k * k;
            dp[i] = min(dp[i], dp[prev] + jumpCost);
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

public static long minCostToReachTop(long[] costs, int n) {
    long INF = Long.MAX_VALUE / 4;
    long[] dp = new long[n + 1];
    Arrays.fill(dp, INF);
    dp[0] = 0;

    for (int i = 1; i <= n; i++) {
        for (int k = 1; k <= 3; k++) {
            int prev = i - k;
            if (prev < 0) break;
            long jumpCost = costs[i] + 1L * k * k;
            dp[i] = Math.min(dp[i], dp[prev] + jumpCost);
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

long long minCostToReachTop(long long* costs, int n) {
    const long long INF = LLONG_MAX / 4;
    long long dp[n + 1];

    for (int i = 0; i <= n; i++)
        dp[i] = INF;

    dp[0] = 0;

    for (int i = 1; i <= n; i++) {
        for (int k = 1; k <= 3; k++) {
            int prev = i - k;
            if (prev < 0) break;
            long long jumpCost = costs[i] + 1LL * k * k;
            long long candidate = dp[prev] + jumpCost;
            if (candidate < dp[i]) dp[i] = candidate;
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

function minCostToReachTop(costs, n) {
  const INF = Number.MAX_SAFE_INTEGER;
  const dp = new Array(n + 1).fill(INF);
  dp[0] = 0;

  for (let i = 1; i <= n; i++) {
    for (let k = 1; k <= 3; k++) {
      let prev = i - k;
      if (prev < 0) break;
      let jumpCost = costs[i] + k * k;
      dp[i] = Math.min(dp[i], dp[prev] + jumpCost);
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

def min_cost_to_reach_top(costs, n):
    INF = 10**30
    dp = [INF] * (n + 1)
    dp[0] = 0

    for i in range(1, n + 1):
        for k in range(1, 4):
            prev = i - k
            if prev < 0:
                break
            jumpCost = costs[i] + k * k
            dp[i] = min(dp[i], dp[prev] + jumpCost)

    return dp[n]

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512
