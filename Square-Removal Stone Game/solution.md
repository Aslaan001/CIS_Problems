## CPP

### SOLUTION

bool winnerSquareGame(int n) {
    vector<bool> dp(n + 1, false);
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j * j <= i; j++) {
            if (dp[i - j * j] == false) {
                dp[i] = true;
                break;
            }
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

public static boolean winnerSquareGame(int n) {
    boolean[] dp = new boolean[n + 1];
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j * j <= i; j++) {
            if (!dp[i - j * j]) {
                dp[i] = true;
                break;
            }
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

bool winnerSquareGame(int n) {
    bool dp[n + 1];
    for (int i = 0; i <= n; i++) dp[i] = false;

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j * j <= i; j++) {
            if (dp[i - j * j] == false) {
                dp[i] = true;
                break;
            }
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

function winnerSquareGame(n) {
  const dp = new Array(n + 1).fill(false);
  for (let i = 1; i <= n; i++) {
    for (let j = 1; j * j <= i; j++) {
      if (!dp[i - j * j]) {
        dp[i] = true;
        break;
      }
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

def winner_square_game(n):
    dp = [False] * (n + 1)
    for i in range(1, n + 1):
        j = 1
        while j * j <= i:
            if not dp[i - j * j]:
                dp[i] = True
                break
            j += 1
    return dp[n]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
