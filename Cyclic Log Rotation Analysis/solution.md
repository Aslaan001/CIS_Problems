## CPP

### SOLUTION

int stringTransformation(string s, string t, long long k) {
    const int mod = 1e9 + 7;
    int n = s.size();

    if (k == 0) return s == t;

    auto zAlgo = [&](const string& str) {
        int m = str.size();
        vector<int> Z(m);
        int l = 0, r = 0;
        for (int i = 1; i < m; i++) {
            if (i <= r) Z[i] = min(Z[i - l], r - i + 1);
            while (i + Z[i] < m && str[Z[i]] == str[i + Z[i]]) Z[i]++;
            if (i + Z[i] - 1 > r) {
                l = i;
                r = i + Z[i] - 1;
            }
        }
        return Z;
    };

    string S = t + s + s;
    vector<int> Z = zAlgo(S);

    int x = 0;
    for (int i = n; i < 2 * n; i++)
        if (Z[i] >= n) x++;

    vector<vector<long long>> mat = {
        {x - 1, x},
        {n - x, n - x - 1}
    };

    auto mul = [&](vector<vector<long long>>& a, vector<vector<long long>>& b) {
        vector<vector<long long>> c(2, vector<long long>(2));
        for (int i = 0; i < 2; i++)
            for (int j = 0; j < 2; j++)
                for (int k = 0; k < 2; k++)
                    c[i][j] = (c[i][j] + a[i][k] * b[k][j]) % mod;
        return c;
    };

    vector<vector<long long>> res = {{1, 0}, {0, 1}};
    while (k > 0) {
        if (k & 1) res = mul(res, mat);
        mat = mul(mat, mat);
        k >>= 1;
    }

    vector<long long> v = (s == t) ? vector<long long>{1, 0} : vector<long long>{0, 1};
    return (res[0][0] * v[0] + res[0][1] * v[1]) % mod;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int stringTransformation(String s, String t, long k) {
    final int mod = 1000000007;
    int n = s.length();

    if (k == 0) return s.equals(t) ? 1 : 0;

    String S = t + s + s;
    int m = S.length();
    int[] Z = new int[m];

    for (int i = 1, l = 0, r = 0; i < m; i++) {
        if (i <= r) Z[i] = Math.min(Z[i - l], r - i + 1);
        while (i + Z[i] < m && S.charAt(Z[i]) == S.charAt(i + Z[i])) Z[i]++;
        if (i + Z[i] - 1 > r) {
            l = i;
            r = i + Z[i] - 1;
        }
    }

    int x = 0;
    for (int i = n; i < 2 * n; i++)
        if (Z[i] >= n) x++;

    long[][] mat = {
        {x - 1, x},
        {n - x, n - x - 1}
    };

    long[][] res = {{1, 0}, {0, 1}};

    while (k > 0) {
        if ((k & 1) == 1) res = mul(res, mat, mod);
        mat = mul(mat, mat, mod);
        k >>= 1;
    }

    long[] v = s.equals(t) ? new long[]{1, 0} : new long[]{0, 1};
    return (int)((res[0][0] * v[0] + res[0][1] * v[1]) % mod);
}

static long[][] mul(long[][] a, long[][] b, int mod) {
    long[][] c = new long[2][2];
    for (int i = 0; i < 2; i++)
        for (int j = 0; j < 2; j++)
            for (int k = 0; k < 2; k++)
                c[i][j] = (c[i][j] + a[i][k] * b[k][j]) % mod;
    return c;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int stringTransformation(char* s, char* t, long long k) {
    const int mod = 1000000007;
    int n = strlen(s);

    if (k == 0) return strcmp(s, t) == 0;

    char* S = (char*)malloc(3 * n + 1);
    strcpy(S, t);
    strcat(S, s);
    strcat(S, s);

    int m = strlen(S);
    int* Z = (int*)calloc(m, sizeof(int));

    for (int i = 1, l = 0, r = 0; i < m; i++) {
        if (i <= r) Z[i] = (Z[i - l] < r - i + 1) ? Z[i - l] : r - i + 1;
        while (i + Z[i] < m && S[Z[i]] == S[i + Z[i]]) Z[i]++;
        if (i + Z[i] - 1 > r) {
            l = i;
            r = i + Z[i] - 1;
        }
    }

    int x = 0;
    for (int i = n; i < 2 * n; i++)
        if (Z[i] >= n) x++;

    long long mat[2][2] = {{x - 1, x}, {n - x, n - x - 1}};
    long long res[2][2] = {{1, 0}, {0, 1}};

    while (k > 0) {
        if (k & 1) mul(res, mat, mod);
        mul(mat, mat, mod);
        k >>= 1;
    }

    long long v0 = strcmp(s, t) == 0;
    long long v1 = !v0;
    return (res[0][0] * v0 + res[0][1] * v1) % mod;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function stringTransformation(s, t, k) {
    const mod = 1000000007;
    const n = s.length;

    if (k === 0n) return s === t ? 1 : 0;

    const S = t + s + s;
    const Z = Array(S.length).fill(0);

    for (let i = 1, l = 0, r = 0; i < S.length; i++) {
        if (i <= r) Z[i] = Math.min(Z[i - l], r - i + 1);
        while (i + Z[i] < S.length && S[Z[i]] === S[i + Z[i]]) Z[i]++;
        if (i + Z[i] - 1 > r) {
            l = i;
            r = i + Z[i] - 1;
        }
    }

    let x = 0;
    for (let i = n; i < 2 * n; i++) if (Z[i] >= n) x++;

    function mul(a, b) {
        return [
            [(a[0][0]*b[0][0] + a[0][1]*b[1][0]) % mod,
             (a[0][0]*b[0][1] + a[0][1]*b[1][1]) % mod],
            [(a[1][0]*b[0][0] + a[1][1]*b[1][0]) % mod,
             (a[1][0]*b[0][1] + a[1][1]*b[1][1]) % mod]
        ];
    }

    let mat = [[x - 1, x], [n - x, n - x - 1]];
    let res = [[1, 0], [0, 1]];

    while (k > 0n) {
        if (k & 1n) res = mul(res, mat);
        mat = mul(mat, mat);
        k >>= 1n;
    }

    const v = (s === t) ? [1, 0] : [0, 1];
    return (res[0][0] * v[0] + res[0][1] * v[1]) % mod;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def stringTransformation(s, t, k):
    mod = 10**9 + 7
    n = len(s)

    if k == 0:
        return 1 if s == t else 0

    S = t + s + s
    Z = [0] * len(S)
    l = r = 0
    for i in range(1, len(S)):
        if i <= r:
            Z[i] = min(Z[i - l], r - i + 1)
        while i + Z[i] < len(S) and S[Z[i]] == S[i + Z[i]]:
            Z[i] += 1
        if i + Z[i] - 1 > r:
            l, r = i, i + Z[i] - 1

    x = sum(1 for i in range(n, 2 * n) if Z[i] >= n)

    mat = [
        [x - 1, x],
        [n - x, n - x - 1]
    ]

    def mul(a, b):
        return [
            [(a[0][0] * b[0][0] + a[0][1] * b[1][0]) % mod,
             (a[0][0] * b[0][1] + a[0][1] * b[1][1]) % mod],
            [(a[1][0] * b[0][0] + a[1][1] * b[1][0]) % mod,
             (a[1][0] * b[0][1] + a[1][1] * b[1][1]) % mod]
        ]

    res = [[1, 0], [0, 1]]
    while k > 0:
        if k & 1:
            res = mul(res, mat)
        mat = mul(mat, mat)
        k >>= 1

    v = [1, 0] if s == t else [0, 1]
    return (res[0][0] * v[0] + res[0][1] * v[1]) % mod

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
