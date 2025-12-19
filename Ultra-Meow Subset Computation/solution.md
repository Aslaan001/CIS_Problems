## CPP

### SOLUTION

#include <bits/stdc++.h>
#define MOD 1000000007
using namespace std;

static int f[5005][5005];

long long MEOW(int n) {

    long long sum = 0;

    for (int i = 0; i <= n; i++) {
        for (int j = i + 1; j <= 2 * i + 1; j++) {
            int a = min(j - 1, n);
            int b = j - 1 - i;
            int c = max(0, n - j);
            int d = i - b;

            sum = (sum + 1LL * f[a][b] * f[c][d] % MOD * j) % MOD;
        }
    }

    return sum;
}


### METADATA

**TimeLimit**  
2500

**MemoryLimit** 
256



## JAVA

### SOLUTION

static final int MOD = 1000000007;
static long[][] f = new long[5005][5005];

static void init() {
    for (int i = 0; i <= 5000; i++) {
        for (int j = 0; j <= i; j++) {
            if (j == 0) f[i][j] = 1;
            else f[i][j] = (f[i - 1][j - 1] + f[i - 1][j]) % MOD;
        }
    }
}

public static long MEOW(int n) {

    long sum = 0;

    for (int i = 0; i <= n; i++) {
        for (int j = i + 1; j <= 2 * i + 1; j++) {
            int a = Math.min(j - 1, n);
            int b = j - 1 - i;
            int c = Math.max(0, n - j);
            int d = i - b;

            sum = (sum + f[a][b] * f[c][d] % MOD * j) % MOD;
        }
    }

    return sum;
}


### METADATA

**TimeLimit**  
2500

**MemoryLimit** 
256
