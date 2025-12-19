## CPP

### SOLUTION

const ll MOD = 1000000007;

long long countValidPlaques(int n, int k) {

    ll ans = 1;

    for (ll i = 1; i < k; i++)
        ans = (ans * k) % MOD;

    for (ll i = 1; i <= n - k; i++)
        ans = (ans * (n - k)) % MOD;

    return ans;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256



## JAVA

### SOLUTION

static final long MOD = 1000000007L;

public static long countValidPlaques(int n, int k) {

    long ans = 1;

    for (long i = 1; i < k; i++)
        ans = (ans * k) % MOD;

    for (long i = 1; i <= n - k; i++)
        ans = (ans * (n - k)) % MOD;

    return ans;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256
