## CPP

### SOLUTION

long long minBricks(int n, long long h, const vector<long long>& a) {
    static long long f[405][405];
    for (int i = 1; i <= n; i++)
        for (int j = 1; j <= n; j++)
            f[i][j] = 0;

    for (int l = n; l >= 1; l--) {
        for (int r = l + 1; r <= n; r++) {
            for (int k = l; k < r; k++)
                f[l][r] = max(f[l][r], f[l][k] + f[k + 1][r]);
            if (a[l - 1] + h >= a[r - 1] - h)
                f[l][r] += h - (a[r - 1] - a[l - 1] - 1) / 2;
        }
    }

    long long sum = n * 1LL * h;
    return sum - f[1][n];
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512

## JAVA

### SOLUTION

public static long minBricks(int n, long h, long[] a) {
    long[][] f = new long[n + 2][n + 2];

    for (int l = n; l >= 1; l--) {
        for (int r = l + 1; r <= n; r++) {
            for (int k = l; k < r; k++)
                f[l][r] = Math.max(f[l][r], f[l][k] + f[k + 1][r]);
            if (a[l - 1] + h >= a[r - 1] - h)
                f[l][r] += h - (a[r - 1] - a[l - 1] - 1) / 2;
        }
    }

    long sum = n * h;
    return sum - f[1][n];
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
