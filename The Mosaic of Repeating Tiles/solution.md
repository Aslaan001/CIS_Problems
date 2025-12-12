## CPP

### SOLUTION

long long countNicePaths(int n, int k, const vector<int>& a) {

    static int f[105][105];
    const long long mod = 1000000007;

    for (int i = 0; i <= n; i++)
        for (int j = 0; j <= n; j++)
            f[i][j] = 0;

    f[0][0] = 1;

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++) {

            for (int p = 0; p < i; p++) {

                if (j % k == 1)
                    f[i][j] = (f[i][j] + f[p][j - 1]) % mod;

                else if (p > 0)
                    f[i][j] = (f[i][j] + (a[i - 1] == a[p - 1]) * 1LL * f[p][j - 1]) % mod;
            }
        }
    }

    for (int len = n; len >= 1; len--) {
        if (len % k == 0) {
            long long ans = 0;
            for (int i = 1; i <= n; i++)
                ans = (ans + f[i][len]) % mod;
            if (ans) return ans;
        }
    }

    return 1;
}

### METADATA

**TimeLimit**  
5000

**MemoryLimit**  
256



## JAVA

### SOLUTION

public static long countNicePaths(int n, int k, int[] a) {

    long mod = 1000000007L;
    long[][] f = new long[105][105];

    f[0][0] = 1;

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++) {

            for (int p = 0; p < i; p++) {

                if (j % k == 1) {
                    f[i][j] = (f[i][j] + f[p][j - 1]) % mod;
                }

                else if (p > 0) {
                    if (a[i - 1] == a[p - 1])
                        f[i][j] = (f[i][j] + f[p][j - 1]) % mod;
                }
            }
        }
    }

    for (int len = n; len >= 1; len--) {
        if (len % k == 0) {
            long ans = 0;
            for (int i = 1; i <= n; i++)
                ans = (ans + f[i][len]) % mod;
            if (ans != 0) return ans;
        }
    }

    return 1;
}

### METADATA

**TimeLimit**  
5000

**MemoryLimit**  
256
