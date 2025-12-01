## CPP

### SOLUTION

using ll = long long;

const int MAXN = 100;
const ll MOD = 998244353;

int a[MAXN+5];
int f[MAXN+5][MAXN+5][12][12];
ll C[MAXN+5][MAXN+5];
int n;

int solveDp(int L, int R, int x, int y) {
    if (a[L] == -1) x = 0;
    if (a[R] == -1) y = 0;
    if (x < 0 || y < 0) return 0;

    if (L + 1 == R) {
        if (x == 0 && y == 0) return 1;
        return 0;
    }

    int &res = f[L][R][x][y];
    if (res != -1) return res;

    ll ans = 0;

    for (int i = L + 1; i < R; i++) {
        int li = (a[i] == -1 ? 0 : a[i]);

        int leftSize = i - L - 1;
        int rightSize = R - i - 1;

        int X = x, Y = y;

        if (L > 0 || R < n + 1) {
            if (L == 0) {
                Y--;
            } 
            else if (R == n + 1) {
                X--;
            } 
            else {
                if (i - L <= R - i) X--;
                else Y--;
            }
        }

        for (int j = 0; j <= li; j++) {
            ll t1 = solveDp(L, i, X, j);
            ll t2 = solveDp(i, R, li - j, Y);
            ans = (ans + t1 * t2 % MOD * C[leftSize + rightSize][rightSize]) % MOD;
        }
    }

    return res = ans;
}

ll reconstructPainting(int N, const vector<int> &s) {
    n = N;

    int sum = 0, mx = 0;
    for (int i = 1; i <= n; i++) {
        a[i] = s[i - 1];
        if (a[i] != -1) {
            sum += a[i];
            mx = max(mx, a[i]);
        }
    }

    if (sum >= n || mx >= 12) return 0;

    a[0] = a[n + 1] = 0;

    memset(f, -1, sizeof(f));

    return solveDp(0, n + 1, 0, 0);
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

static final int N = 100;
    static final long MOD = 998244353;

    static int[][][][] f = new int[N+5][N+5][12][12];
    static int[] a = new int[N+5];
    static long[][] C = new long[N+5][N+5];
    static boolean built = false;
    static int nn;

    static int solveSegment(int L, int R, int X, int Y){
        if(a[L] == -1) X = 0;
        if(a[R] == -1) Y = 0;
        if(X < 0 || Y < 0) return 0;

        if(L + 1 == R){
            if(X != 0 || Y != 0) return 0;
            return 1;
        }

        if(f[L][R][X][Y] != -1) return f[L][R][X][Y];

        long ans = 0;

        for(int i = L + 1; i < R; i++){
            int n1 = i - L - 1;
            int n2 = R - i - 1;
            int li = (a[i] == -1 ? 0 : a[i]);

            int x1 = X, y1 = Y;

            if(L > 0 || R != nn+1){
                if(L == 0) y1--;
                else if(R == nn+1) x1--;
                else{
                    if(i - L <= R - i) x1--;
                    else y1--;
                }
            }

            for(int j = 0; j <= li; j++){
                long t1 = solveSegment(L, i, x1, j);
                long t2 = solveSegment(i, R, li - j, y1);
                ans = (ans + t1 * t2 % MOD * C[n1+n2][n2]) % MOD;
            }
        }

        return f[L][R][X][Y] = (int)ans;
    }

    static long reconstructPainting(int n, int[] s){
        nn = n;

        if(!built){
            C[0][0] = 1;
            for(int i = 1; i <= N; i++){
                C[i][0] = 1;
                for(int j = 1; j <= i; j++)
                    C[i][j] = (C[i-1][j-1] + C[i-1][j]) % MOD;
            }
            built = true;
        }

        int sum = 0, mx = 0;

        for(int i = 1; i <= n; i++){
            a[i] = s[i-1];
            if(a[i] != -1){
                sum += a[i];
                mx = Math.max(mx, a[i]);
            }
        }

        if(sum >= n || mx >= 12) return 0;

        a[0] = a[n+1] = 0;

        for(int i = 0; i <= n+1; i++)
            for(int j = 0; j <= n+1; j++)
                for(int x = 0; x < 12; x++)
                    Arrays.fill(f[i][j][x], -1);

        return solveSegment(0, n+1, 0, 0);
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



