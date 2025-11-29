## CPP

### SOLUTION

int countValidSequences(int n) {
    const long long MOD = 1000000007;
    long long ans = 1;
    for (long long i = 1; i <= n; i++) {
        ans = ans * (2 * i - 1) % MOD;
        ans = ans * i % MOD;
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

public static int countValidSequences(int n) {
    long MOD = 1000000007;
    long ans = 1;
    for (long i = 1; i <= n; i++) {
        ans = (ans * (2 * i - 1)) % MOD;
        ans = (ans * i) % MOD;
    }
    return (int) ans;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

long long countValidSequences(int n) {
    const long long MOD = 1000000007;
    long long ans = 1;
    for (long long i = 1; i <= n; i++) {
        ans = (ans * (2 * i - 1)) % MOD;
        ans = (ans * i) % MOD;
    }
    return ans;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function countValidSequences(n) {
  const MOD = 1000000007n;
  let ans = 1n;
  for (let i = 1n; i <= BigInt(n); i++) {
    ans = (ans * (2n * i - 1n)) % MOD;
    ans = (ans * i) % MOD;
  }
  return Number(ans);
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def count_valid_sequences(n):
    MOD = 10**9 + 7
    ans = 1
    for i in range(1, n + 1):
        ans = (ans * (2 * i - 1)) % MOD
        ans = (ans * i) % MOD
    return ans

### METADATA

TimeLimit  
1000

MemoryLimit  
512
