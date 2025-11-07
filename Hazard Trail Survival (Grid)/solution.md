## CPP

### SOLUTION

int minInitialHealth(vector<vector<int>>& dungeon) {
    int m = dungeon.size(), n = dungeon[0].size();
    vector<vector<int>> dp(m, vector<int>(n, 0));
    dp[m-1][n-1] = max(1, 1 - dungeon[m-1][n-1]);

    for (int i = m - 2; i >= 0; i--) {
        dp[i][n-1] = max(1, dp[i+1][n-1] - dungeon[i][n-1]);
    }
    for (int j = n - 2; j >= 0; j--) {
        dp[m-1][j] = max(1, dp[m-1][j+1] - dungeon[m-1][j]);
    }

    for (int i = m - 2; i >= 0; i--) {
        for (int j = n - 2; j >= 0; j--) {
            int need = min(dp[i+1][j], dp[i][j+1]) - dungeon[i][j];
            dp[i][j] = max(1, need);
        }
    }

    return dp[0][0];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int minInitialHealth(int[][] dungeon) {
    int m = dungeon.length, n = dungeon[0].length;
    int[][] dp = new int[m][n];
    dp[m-1][n-1] = Math.max(1, 1 - dungeon[m-1][n-1]);

    for (int i = m - 2; i >= 0; i--) {
        dp[i][n-1] = Math.max(1, dp[i+1][n-1] - dungeon[i][n-1]);
    }
    for (int j = n - 2; j >= 0; j--) {
        dp[m-1][j] = Math.max(1, dp[m-1][j+1] - dungeon[m-1][j]);
    }

    for (int i = m - 2; i >= 0; i--) {
        for (int j = n - 2; j >= 0; j--) {
            int need = Math.min(dp[i+1][j], dp[i][j+1]) - dungeon[i][j];
            dp[i][j] = Math.max(1, need);
        }
    }

    return dp[0][0];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

int minInitialHealth(int dungeon[][200], int m, int n) {
    int dp[200][200];

    dp[m-1][n-1] = 1 - dungeon[m-1][n-1];
    if (dp[m-1][n-1] < 1) dp[m-1][n-1] = 1;

    for (int i = m - 2; i >= 0; i--) {
        dp[i][n-1] = dp[i+1][n-1] - dungeon[i][n-1];
        if (dp[i][n-1] < 1) dp[i][n-1] = 1;
    }
    for (int j = n - 2; j >= 0; j--) {
        dp[m-1][j] = dp[m-1][j+1] - dungeon[m-1][j];
        if (dp[m-1][j] < 1) dp[m-1][j] = 1;
    }

    for (int i = m - 2; i >= 0; i--) {
        for (int j = n - 2; j >= 0; j--) {
            int need = dp[i+1][j] < dp[i][j+1] ? dp[i+1][j] : dp[i][j+1];
            need -= dungeon[i][j];
            dp[i][j] = need < 1 ? 1 : need;
        }
    }

    return dp[0][0];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function minInitialHealth(dungeon) {
  const m = dungeon.length, n = dungeon[0].length;
  const dp = Array.from({ length: m }, () => Array(n).fill(0));

  dp[m-1][n-1] = Math.max(1, 1 - dungeon[m-1][n-1]);

  for (let i = m - 2; i >= 0; i--) {
    dp[i][n-1] = Math.max(1, dp[i+1][n-1] - dungeon[i][n-1]);
  }
  for (let j = n - 2; j >= 0; j--) {
    dp[m-1][j] = Math.max(1, dp[m-1][j+1] - dungeon[m-1][j]);
  }

  for (let i = m - 2; i >= 0; i--) {
    for (let j = n - 2; j >= 0; j--) {
      let need = Math.min(dp[i+1][j], dp[i][j+1]) - dungeon[i][j];
      dp[i][j] = Math.max(1, need);
    }
  }

  return dp[0][0];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def min_initial_health(dungeon):
    m, n = len(dungeon), len(dungeon[0])
    dp = [[0]*n for _ in range(m)]
    dp[m-1][n-1] = max(1, 1 - dungeon[m-1][n-1])

    for i in range(m-2, -1, -1):
        dp[i][n-1] = max(1, dp[i+1][n-1] - dungeon[i][n-1])
    for j in range(n-2, -1, -1):
        dp[m-1][j] = max(1, dp[m-1][j+1] - dungeon[m-1][j])

    for i in range(m-2, -1, -1):
        for j in range(n-2, -1, -1):
            need = min(dp[i+1][j], dp[i][j+1]) - dungeon[i][j]
            dp[i][j] = max(1, need)

    return dp[0][0]

### METADATA

TimeLimit  
1000

MemoryLimit  
512
