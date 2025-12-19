## CPP

### SOLUTION

static const int MOD = 1000003;

long long countWalls(int n, int C) {

    long long a = 1, b = 1, inv = 1;

    for (int i = 1; i <= C; i++) {
        a = a * (n + i) % MOD;
        b = b * i % MOD;
    }

    for (int i = 1; i <= MOD - 2; i++)
        inv = inv * b % MOD;

    return (a * inv % MOD - 1 + MOD) % MOD;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256



## JAVA

### SOLUTION

static final int MOD = 1000003;

public static long countWalls(int n, int C) {

    long a = 1, b = 1, inv = 1;

    for (int i = 1; i <= C; i++) {
        a = (a * (n + i)) % MOD;
        b = (b * i) % MOD;
    }

    for (int i = 1; i <= MOD - 2; i++)
        inv = (inv * b) % MOD;

    return (a * inv % MOD - 1 + MOD) % MOD;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256
