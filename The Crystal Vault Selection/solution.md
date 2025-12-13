## CPP

### SOLUTION

long long minCubeSum(int n, const vector<vector<vector<long long>>>& cube) {

    static long long dp[1 << 24];
    static int ppc[1 << 12];

    for (int i = 1; i < (1 << n); i++)
        ppc[i] = ppc[i ^ (i & -i)] + 1;

    int FULL = 1 << (2 * n);
    memset(dp, 0x3f, sizeof(dp));
    dp[0] = 0;

    for (int mask = 1; mask < FULL; mask++) {

        int maskX = mask >> n;
        int maskY = mask & ((1 << n) - 1);

        if (ppc[maskX] != ppc[maskY]) continue;

        int p = ppc[maskX];

        for (int i = 0; i < n; i++) {
            if (!(maskX & (1 << i))) continue;

            for (int j = 0; j < n; j++) {
                if (!(maskY & (1 << j))) continue;

                int prev = mask ^ (1 << (i + n)) ^ (1 << j);
                dp[mask] = min(dp[mask], dp[prev] + cube[p - 1][i][j]);
            }
        }
    }

    return dp[FULL - 1];
}

### METADATA

**TimeLimit**  
3000

**MemoryLimit**  
1024



## JAVA

### SOLUTION

public static long minCubeSum(int n, long[][][] cube) {

        int FULL = 1 << (2 * n);

        long[] dp = new long[FULL];
        Arrays.fill(dp, INF);
        dp[0] = 0;

        int[] ppc = new int[1 << n];
        for (int i = 1; i < (1 << n); i++) {
            ppc[i] = ppc[i ^ (i & -i)] + 1;
        }

        for (int mask = 1; mask < FULL; mask++) {

            int maskX = mask >> n;
            int maskY = mask & ((1 << n) - 1);

            if (ppc[maskX] != ppc[maskY]) continue;

            int p = ppc[maskX];

            for (int i = 0; i < n; i++) {
                if ((maskX & (1 << i)) == 0) continue;

                for (int j = 0; j < n; j++) {
                    if ((maskY & (1 << j)) == 0) continue;

                    int prev = mask ^ (1 << (i + n)) ^ (1 << j);
                    dp[mask] = Math.min(dp[mask], dp[prev] + cube[p - 1][i][j]);
                }
            }
        }

        return dp[FULL - 1];
}

### METADATA

**TimeLimit**  
3000

**MemoryLimit**  
1024
