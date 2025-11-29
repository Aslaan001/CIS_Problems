## CPP

### SOLUTION

int raceCar(int t) {
    vector<int> dp(t + 1, INT_MAX);
    int r = 1;
    for (int i = 1; i <= t; i++) {
        int upper = (1 << r) - 1;
        if (i == upper) {
            dp[i] = r;
            r++;
        } else {
            int u = (1 << r) - 1;
            int l = (1 << (r - 1)) - 1;
            for (int j = 0; j < r - 1; j++) {
                int back = (1 << j) - 1;
                dp[i] = min(dp[i], (r - 1) + 1 + 1 + j + dp[i - l + back]);
            }
            dp[i] = min(dp[i], r + 1 + dp[u - i]);
        }
    }
    return dp[t];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int raceCar(int t) {
    int[] dp = new int[t + 1];
    int r = 1;
    for (int i = 1; i <= t; i++) {
        dp[i] = Integer.MAX_VALUE;
        int upper = (1 << r) - 1;
        if (i == upper) {
            dp[i] = r;
            r++;
        } else {
            int u = (1 << r) - 1;
            int l = (1 << (r - 1)) - 1;
            for (int j = 0; j < r - 1; j++) {
                int back = (1 << j) - 1;
                dp[i] = Math.min(dp[i], (r - 1) + 1 + 1 + j + dp[i - l + back]);
            }
            dp[i] = Math.min(dp[i], r + 1 + dp[u - i]);
        }
    }
    return dp[t];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int raceCar(int t) {
    int dp[t + 1];
    for (int i = 0; i <= t; i++) dp[i] = 2147483647;
    int r = 1;
    for (int i = 1; i <= t; i++) {
        int upper = (1 << r) - 1;
        if (i == upper) {
            dp[i] = r;
            r++;
        } else {
            int u = (1 << r) - 1;
            int l = (1 << (r - 1)) - 1;
            for (int j = 0; j < r - 1; j++) {
                int back = (1 << j) - 1;
                int remain = i - l + back;
                int cost = (r - 1) + 1 + 1 + j + dp[remain];
                if (cost < dp[i]) dp[i] = cost;
            }
            int option = r + 1 + dp[u - i];
            if (option < dp[i]) dp[i] = option;
        }
    }
    return dp[t];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function raceCar(t) {
  const dp = new Array(t + 1).fill(Infinity);
  let r = 1;
  for (let i = 1; i <= t; i++) {
    let upper = (1 << r) - 1;
    if (i === upper) {
      dp[i] = r;
      r++;
    } else {
      let u = (1 << r) - 1;
      let l = (1 << (r - 1)) - 1;
      for (let j = 0; j < r - 1; j++) {
        let back = (1 << j) - 1;
        dp[i] = Math.min(dp[i], (r - 1) + 1 + 1 + j + dp[i - l + back]);
      }
      dp[i] = Math.min(dp[i], r + 1 + dp[u - i]);
    }
  }
  return dp[t];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def race_car(t):
    dp = [10**9] * (t + 1)
    r = 1
    for i in range(1, t + 1):
        upper = (1 << r) - 1
        if i == upper:
            dp[i] = r
            r += 1
        else:
            u = (1 << r) - 1
            l = (1 << (r - 1)) - 1
            for j in range(0, r - 1):
                back = (1 << j) - 1
                dp[i] = min(dp[i], (r - 1) + 1 + 1 + j + dp[i - l + back])
            dp[i] = min(dp[i], r + 1 + dp[u - i])
    return dp[t]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
