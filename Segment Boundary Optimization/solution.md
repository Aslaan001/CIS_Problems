## CPP

### SOLUTION

long long minimumCost(vector<int>& p, vector<long long>& w, int n) {
    const long long INF = (long long)1e18;

    int size = 1;
    while (size <= n) size <<= 1;

    vector<long long> seg(size * 2, 0), lazy(size * 2, 0);

    auto push = [&](int x) {
        if (lazy[x] != 0) {
            for (int c : {x << 1, x << 1 | 1}) {
                seg[c] += lazy[x];
                lazy[c] += lazy[x];
            }
            lazy[x] = 0;
        }
    };

    function<void(int,int,int,int,int,long long)> update =
        [&](int x, int l, int r, int L, int R, long long val) {
            if (l <= L && R <= r) {
                seg[x] += val;
                lazy[x] += val;
                return;
            }
            push(x);
            int mid = (L + R) >> 1;
            if (l <= mid) update(x << 1, l, r, L, mid, val);
            if (r > mid) update(x << 1 | 1, l, r, mid + 1, R, val);
            seg[x] = min(seg[x << 1], seg[x << 1 | 1]);
        };

    for (int i = 0; i < n; i++) {
        update(1, p[i], n, 0, n, w[i]);
    }

    long long tot = 0, ans = INF;

    for (int i = 0; i < n - 1; i++) {
        tot += w[i];
        update(1, p[i], n, 0, n, -2 * w[i]);
        ans = min(ans, seg[1] + tot);
    }

    return ans;
}

### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256




## JAVA

### SOLUTION

static long minimumCost(int[] p, long[] w, int n) {
    long INF = (long)1e18;

    int size = 1;
    while (size <= n) size <<= 1;

    long[] seg = new long[size * 2];
    long[] lazy = new long[size * 2];

    class SegTree {
        void push(int x) {
            if (lazy[x] != 0) {
                for (int c : new int[]{x << 1, x << 1 | 1}) {
                    seg[c] += lazy[x];
                    lazy[c] += lazy[x];
                }
                lazy[x] = 0;
            }
        }

        void update(int x, int l, int r, int L, int R, long val) {
            if (l <= L && R <= r) {
                seg[x] += val;
                lazy[x] += val;
                return;
            }
            push(x);
            int mid = (L + R) >> 1;
            if (l <= mid) update(x << 1, l, r, L, mid, val);
            if (r > mid) update(x << 1 | 1, l, r, mid + 1, R, val);
            seg[x] = Math.min(seg[x << 1], seg[x << 1 | 1]);
        }
    }

    SegTree st = new SegTree();

    for (int i = 0; i < n; i++) {
        st.update(1, p[i], n, 0, n, w[i]);
    }

    long tot = 0, ans = INF;

    for (int i = 0; i < n - 1; i++) {
        tot += w[i];
        st.update(1, p[i], n, 0, n, -2 * w[i]);
        ans = Math.min(ans, seg[1] + tot);
    }

    return ans;
}

### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256
