## CPP
long long countNicknamePairs(const string& A, const string& B) {

    int n = A.size(), m = B.size();
    static int c1[30], c2[30];
    static long long dp[27][200001];
    static long long tt[400001], intt[400001];
    long long mod = 998244353;

    for (int i = 0; i < 30; i++) c1[i] = c2[i] = 0;

    for (int i = 0; i <= 26; i++)
        for (int j = 0; j <= m; j++)
            dp[i][j] = 0;

    tt[0] = 1;
    intt[0] = 1;
    tt[1] = 1;
    intt[1] = 1;

    for (int i = 2; i <= 400000; i++) {
        tt[i] = i;
        intt[i] = (mod - mod / i) * intt[mod % i] % mod;
    }

    for (int i = 2; i <= 400000; i++) {
        tt[i] = tt[i] * tt[i - 1] % mod;
        intt[i] = intt[i] * intt[i - 1] % mod;
    }

    for (int i = 0; i < n; i++) c1[A[i] - 'A']++;
    for (int i = 0; i < m; i++) c2[B[i] - 'A']++;

    dp[0][c2[0]] = 1;

    for (int i = 0; i < 26; i++) {
        int t = c2[i];
        long long cur = 0;
        for (int j = 0; j <= c2[i + 1] && j <= c1[i]; j++) {
            int x = c1[i] - j;
            while (t >= x) {
                cur = (cur + dp[i][t]) % mod;
                t--;
            }
            dp[i + 1][c2[i + 1] - j] = cur * intt[j] % mod * intt[x] % mod;
        }
    }

    return dp[26][0] * tt[n] % mod;
}



## JAVA


    static final long mod = 998244353L;
    static long[][] dp = new long[27][200001];
    static int[] c1 = new int[30];
    static int[] c2 = new int[30];
    static long[] tt = new long[400001];
    static long[] intt = new long[400001];

    public static long countNicknamePairs(String A, String B) {

        int n = A.length(), m = B.length();

        Arrays.fill(c1, 0);
        Arrays.fill(c2, 0);

        for (int i = 0; i <= 26; i++)
            Arrays.fill(dp[i], 0, m + 1, 0);

        tt[0] = 1;
        intt[0] = 1;
        tt[1] = 1;
        intt[1] = 1;

        for (int i = 2; i <= 400000; i++) {
            tt[i] = i;
            intt[i] = (mod - (mod / i)) * intt[(int)(mod % i)] % mod;
        }

        for (int i = 2; i <= 400000; i++) {
            tt[i] = tt[i] * tt[i - 1] % mod;
            intt[i] = intt[i] * intt[i - 1] % mod;
        }

        for (int i = 0; i < n; i++) c1[A.charAt(i) - 'A']++;
        for (int i = 0; i < m; i++) c2[B.charAt(i) - 'A']++;

        dp[0][c2[0]] = 1;

        for (int i = 0; i < 26; i++) {
            int t = c2[i];
            long cur = 0;
            for (int j = 0; j <= c2[i + 1] && j <= c1[i]; j++) {
                int x = c1[i] - j;
                while (t >= x) {
                    cur = (cur + dp[i][t]) % mod;
                    t--;
                }
                dp[i + 1][c2[i + 1] - j] = cur * intt[j] % mod * intt[x] % mod;
            }
        }

        return dp[26][0] * tt[n] % mod;
    }