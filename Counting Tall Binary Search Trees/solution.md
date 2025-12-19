## CPP

### SOLUTION

long long countTallBST(int n, int h) {

    static long long f[45][45] = {0};

    for (int i = 1; i <= n; i++) {
        f[0][i - 1] = 1;
        for (int j = 1; j <= n; j++) {
            for (int k = 0; k < j; k++) {
                f[j][i] += f[k][i - 1] * f[j - k - 1][i - 1];
            }
        }
    }

    return f[n][n] - f[n][h - 1];
}


### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
64



## JAVA

### SOLUTION

static long[][] f = new long[45][45];

public static long countTallBST(int n, int h) {

    for (int i = 1; i <= n; i++) {
        f[0][i - 1] = 1;
        for (int j = 1; j <= n; j++) {
            for (int k = 0; k < j; k++) {
                f[j][i] += f[k][i - 1] * f[j - k - 1][i - 1];
            }
        }
    }

    return f[n][n] - f[n][h - 1];
}


### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
64
