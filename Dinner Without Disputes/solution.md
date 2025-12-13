## CPP

### SOLUTION

vector<long long> countValidPairs(int n, int m, const vector<string>& likes, const vector<int>& a) {

    static long long mul[25][1 << 20];
    static long long ans[25][1 << 20];
    static long long fin[1 << 20];
    static long long res[400005];

    memset(mul, 0, sizeof(mul));
    memset(ans, 0, sizeof(ans));
    memset(fin, 0, sizeof(fin));
    memset(res, 0, sizeof(res));

    int S = 0, tot = 0;
    vector<int> T(m);

    for (int i = 0; i < m; i++) {
        for (char ch : likes[i])
            T[i] |= (1 << (ch - 'A'));
    }

    for (int i = 0; i < n; i++) {
        tot += a[i];
        if (a[i] & 1)
            S |= (1 << i);
    }

    for (int i = 0; i < m; i++)
        mul[__builtin_popcount(T[i] & S)][T[i]]++;

    for (int i = 0; i <= n; i++)
        for (int j = 0; j < n; j++)
            for (int k = 0; k < (1 << n); k++)
                if (k & (1 << j))
                    mul[i][k] += mul[i][k ^ (1 << j)];

    for (int i = 0; i <= n; i++)
        for (int j = 0; j <= n - i; j++)
            for (int k = 0; k < (1 << n); k++)
                ans[i + j][k] += mul[i][k] * mul[j][k];

    for (int i = 0; i <= n; i++)
        for (int j = 0; j < n; j++)
            for (int k = 0; k < (1 << n); k++)
                if (k & (1 << j))
                    ans[i][k] -= ans[i][k ^ (1 << j)];

    for (int i = 0; i <= n; i++)
        for (int k = 0; k < (1 << n); k++)
            if (i == __builtin_popcount(k & S))
                fin[k] += ans[i][k];

    for (int i = 0; i < m; i++)
        if ((T[i] & S) == 0)
            fin[T[i]]--;

    for (int k = 0; k < (1 << n); k++)
        fin[k] >>= 1;

    for (int k = 0; k < (1 << n); k++) {
        int eat = 0;
        for (int i = 0; i < n; i++)
            if (!(k & (1 << i)))
                eat += a[i];
        res[eat] += fin[k];
    }

    vector<long long> out(tot + 1);
    for (int i = 0; i <= tot; i++)
        out[i] = res[i];

    return out;
}


### METADATA

**TimeLimit**  
5000

**MemoryLimit**  
256



## JAVA

### SOLUTION

public static long[] countValidPairs(int n, int m, String[] likes, int[] a) {

    int N = 1 << n;
    long[][] mul = new long[n + 1][N];
    long[][] ans = new long[n + 1][N];
    long[] fin = new long[N];

    int S = 0, tot = 0;
    int[] T = new int[m];

    for (int i = 0; i < m; i++) {
        for (char ch : likes[i].toCharArray())
            T[i] |= (1 << (ch - 'A'));
    }

    for (int i = 0; i < n; i++) {
        tot += a[i];
        if ((a[i] & 1) == 1)
            S |= (1 << i);
    }

    for (int i = 0; i < m; i++)
        mul[Integer.bitCount(T[i] & S)][T[i]]++;

    for (int i = 0; i <= n; i++)
        for (int j = 0; j < n; j++)
            for (int k = 0; k < N; k++)
                if ((k & (1 << j)) != 0)
                    mul[i][k] += mul[i][k ^ (1 << j)];

    for (int i = 0; i <= n; i++)
        for (int j = 0; j <= n - i; j++)
            for (int k = 0; k < N; k++)
                ans[i + j][k] += mul[i][k] * mul[j][k];

    for (int i = 0; i <= n; i++)
        for (int j = 0; j < n; j++)
            for (int k = 0; k < N; k++)
                if ((k & (1 << j)) != 0)
                    ans[i][k] -= ans[i][k ^ (1 << j)];

    for (int i = 0; i <= n; i++)
        for (int k = 0; k < N; k++)
            if (i == Integer.bitCount(k & S))
                fin[k] += ans[i][k];

    for (int i = 0; i < m; i++)
        if ((T[i] & S) == 0)
            fin[T[i]]--;

    for (int k = 0; k < N; k++)
        fin[k] >>= 1;

    long[] res = new long[tot + 1];

    for (int k = 0; k < N; k++) {
        int eat = 0;
        for (int i = 0; i < n; i++)
            if ((k & (1 << i)) == 0)
                eat += a[i];
        res[eat] += fin[k];
    }

    return res;
}


### METADATA

**TimeLimit**  
5000

**MemoryLimit**  
256
