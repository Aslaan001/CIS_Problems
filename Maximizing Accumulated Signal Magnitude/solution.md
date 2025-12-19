## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

const long long MOD = 998244353;

long long countMaxMagnitudeWays(int n, const vector<long long>& a) {

    long long l = 0, r = 0;
    long long f = 1, fl = 1;

    for (int i = 0; i < n; i++) {
        long long x = a[i];
        l += x;
        r += x;

        f = f * 2 % MOD;

        if (l >= 0) fl = fl * 2 % MOD;

        if (r == -l && r != l) {
            f = (f + fl) % MOD;
        }

        if (r < -l) {
            f = fl;
        }

        r = max(r, -l);
    }

    return f % MOD;
}


### METADATA

TimeLimit  
2000

MemoryLimit  
256



## JAVA

### SOLUTION

static final long MOD = 998244353L;

public static long countMaxMagnitudeWays(int n, long[] a) {

    long l = 0, r = 0;
    long f = 1, fl = 1;

    for (int i = 0; i < n; i++) {
        long x = a[i];
        l += x;
        r += x;

        f = (f * 2) % MOD;

        if (l >= 0) fl = (fl * 2) % MOD;

        if (r == -l && r != l) {
            f = (f + fl) % MOD;
        }

        if (r < -l) {
            f = fl;
        }

        r = Math.max(r, -l);
    }

    return f % MOD;
}


### METADATA

**MemoryLimit**  
2000

**MemoryLimit**  
256
