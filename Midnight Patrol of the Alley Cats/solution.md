## CPP

### SOLUTION

long long maxFedCats(int n, int m, const vector<pair<int,int>>& seg) {

    vector<int> f(n + 2, 0), cnt(n + 3, 0), g(n + 2, 0);

    for (auto &p : seg) {
        int l = p.first, r = p.second;
        cnt[l]++; 
        cnt[r + 1]--;
        g[l] = max(g[l], r);
    }

    for (int i = 1; i <= n; i++) {
        cnt[i] += cnt[i - 1];
        g[i] = max(g[i], g[i - 1]);
    }

    for (int i = 1; i <= n; i++) {
        f[i] = max(f[i], f[i - 1]);
        f[g[i]] = max(f[g[i]], f[i - 1] + cnt[i]);
    }

    return f[n];
}

### METADATA

**TimeLimit**  
3000

**MemoryLimit**  
512



## JAVA

### SOLUTION

public static long maxFedCats(int n, int m, long[][] seg) {

    int[] f = new int[n + 2];
    int[] cnt = new int[n + 3];
    int[] g = new int[n + 2];

    for (int i = 0; i < m; i++) {
        int l = (int)seg[i][0];
        int r = (int)seg[i][1];
        cnt[l]++;
        cnt[r + 1]--;
        if (g[l] < r) g[l] = r;
    }

    for (int i = 1; i <= n; i++) {
        cnt[i] += cnt[i - 1];
        g[i] = Math.max(g[i], g[i - 1]);
    }

    for (int i = 1; i <= n; i++) {
        f[i] = Math.max(f[i], f[i - 1]);
        int gi = g[i];
        f[gi] = Math.max(f[gi], f[i - 1] + cnt[i]);
    }

    return f[n];
}

### METADATA

**TimeLimit**  
3000

**MemoryLimit**  
512
