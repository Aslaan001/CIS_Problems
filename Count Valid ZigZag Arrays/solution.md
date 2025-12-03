## CPP

### SOLUTION

int countZigZagArrays(int n, int l, int r) {
    const long long MOD = 1000000007;
    int m = r - l + 1;

    if (n == 1) return m;

    vector<long long> up(m + 1, 0), down(m + 1, 0);
    for (int j = 1; j <= m; j++) {
        up[j] = j - 1;
        down[j] = m - j;
    }

    vector<long long> prefix_up(m + 1, 0), prefix_down(m + 1, 0);
    vector<long long> next_up(m + 1, 0), next_down(m + 1, 0);

    for (int len = 3; len <= n; len++) {
        for (int i = 1; i <= m; i++) {
            prefix_up[i] = (prefix_up[i - 1] + up[i]) % MOD;
            prefix_down[i] = (prefix_down[i - 1] + down[i]) % MOD;
        }
        for (int j = 1; j <= m; j++) {
            next_up[j] = prefix_down[j - 1];
            next_down[j] = (prefix_up[m] - prefix_up[j] + MOD) % MOD;
        }
        up = next_up;
        down = next_down;
    }

    long long ans = 0;
    for (int j = 1; j <= m; j++) {
        ans = (ans + up[j] + down[j]) % MOD;
    }

    return (int)ans;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## JAVA

### SOLUTION

public static long countZigZagArrays(int n, int l, int r) {
    long MOD = 1000000007;
    int m = r - l + 1;

    if (n == 1) return m;

    long[] up = new long[m + 1];
    long[] down = new long[m + 1];

    for (int j = 1; j <= m; j++) {
        up[j] = j - 1;
        down[j] = m - j;
    }

    long[] prefix_up = new long[m + 1];
    long[] prefix_down = new long[m + 1];
    long[] next_up = new long[m + 1];
    long[] next_down = new long[m + 1];

    for (int len = 3; len <= n; len++) {
        for (int i = 1; i <= m; i++) {
            prefix_up[i] = (prefix_up[i - 1] + up[i]) % MOD;
            prefix_down[i] = (prefix_down[i - 1] + down[i]) % MOD;
        }
        for (int j = 1; j <= m; j++) {
            next_up[j] = prefix_down[j - 1];
            next_down[j] = (prefix_up[m] - prefix_up[j] + MOD) % MOD;
        }
        up = next_up.clone();
        down = next_down.clone();
    }

    long ans = 0;
    for (int j = 1; j <= m; j++) {
        ans = (ans + up[j] + down[j]) % MOD;
    }

    return ans;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## C

### SOLUTION

long long countZigZagArrays(int n, int l, int r) {
    const long long MOD = 1000000007;
    int m = r - l + 1;

    if (n == 1) return m;

    long long up[m + 1], down[m + 1];
    for (int j = 1; j <= m; j++) {
        up[j] = j - 1;
        down[j] = m - j;
    }

    long long prefix_up[m + 1], prefix_down[m + 1];
    long long next_up[m + 1], next_down[m + 1];

    for (int len = 3; len <= n; len++) {
        prefix_up[0] = prefix_down[0] = 0;
        for (int i = 1; i <= m; i++) {
            prefix_up[i] = (prefix_up[i - 1] + up[i]) % MOD;
            prefix_down[i] = (prefix_down[i - 1] + down[i]) % MOD;
        }
        for (int j = 1; j <= m; j++) {
            next_up[j] = prefix_down[j - 1];
            next_down[j] = (prefix_up[m] - prefix_up[j] + MOD) % MOD;
        }
        for (int j = 1; j <= m; j++) {
            up[j] = next_up[j];
            down[j] = next_down[j];
        }
    }

    long long ans = 0;
    for (int j = 1; j <= m; j++) {
        ans = (ans + up[j] + down[j]) % MOD;
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

function countZigZagArrays(n, l, r) {
  const MOD = 1000000007n;
  const m = BigInt(r - l + 1);

  if (n === 1) return Number(m);

  let up = Array(r - l + 2).fill(0n);
  let down = Array(r - l + 2).fill(0n);

  for (let j = 1; j <= r - l + 1; j++) {
    up[j] = BigInt(j - 1);
    down[j] = BigInt((r - l + 1) - j);
  }

  let prefix_up = Array(r - l + 2).fill(0n);
  let prefix_down = Array(r - l + 2).fill(0n);
  let next_up = Array(r - l + 2).fill(0n);
  let next_down = Array(r - l + 2).fill(0n);

  for (let len = 3; len <= n; len++) {
    prefix_up[0] = prefix_down[0] = 0n;
    for (let i = 1; i <= r - l + 1; i++) {
      prefix_up[i] = (prefix_up[i - 1] + up[i]) % MOD;
      prefix_down[i] = (prefix_down[i - 1] + down[i]) % MOD;
    }
    for (let j = 1; j <= r - l + 1; j++) {
      next_up[j] = prefix_down[j - 1];
      let v = prefix_up[r - l + 1] - prefix_up[j];
      next_down[j] = (v % MOD + MOD) % MOD;
    }
    up = next_up.slice();
    down = next_down.slice();
  }

  let ans = 0n;
  for (let j = 1; j <= r - l + 1; j++) {
    ans = (ans + up[j] + down[j]) % MOD;
  }

  return Number(ans);
}

### METADATA

**TimeLimit**  
4800

**MemoryLimit**  
512


## PYTHON

### SOLUTION

def count_zigzag_arrays(n, l, r):
    MOD = 10**9 + 7
    m = r - l + 1

    if n == 1:
        return m

    up = [0] * (m + 1)
    down = [0] * (m + 1)

    for j in range(1, m + 1):
        up[j] = j - 1
        down[j] = m - j

    prefix_up = [0] * (m + 1)
    prefix_down = [0] * (m + 1)
    next_up = [0] * (m + 1)
    next_down = [0] * (m + 1)

    for _ in range(3, n + 1):
        for i in range(1, m + 1):
            prefix_up[i] = (prefix_up[i - 1] + up[i]) % MOD
            prefix_down[i] = (prefix_down[i - 1] + down[i]) % MOD

        for j in range(1, m + 1):
            next_up[j] = prefix_down[j - 1]
            next_down[j] = (prefix_up[m] - prefix_up[j]) % MOD

        up, down = next_up[:], next_down[:]

    ans = 0
    for j in range(1, m + 1):
        ans = (ans + up[j] + down[j]) % MOD

    return ans

### METADATA

**TimeLimit**  
7000

**MemoryLimit**  
512
