## CPP

### SOLUTION

int cntLucky(ll a, ll b) {
    if (a > b) return 0;
    return 1 + cntLucky(a * 10 + 4, b) + cntLucky(a * 10 + 7, b);
}

bool isLucky(ll a) {
    return a == 0 || ((a % 10 == 4 || a % 10 == 7) && isLucky(a / 10));
}

ll fact[20];
bool used[20];

long long countLuckyPositions(long long n, long long k) {

    k--;

    fact[0] = 1;
    for (int i = 1; i <= 13; i++)
        fact[i] = fact[i - 1] * i;

    if (n <= 13 && fact[n] <= k)
        return -1;

    int ans = cntLucky(0, n) - 1;

    for (int i = 13; i >= 0; i--) {
        ll shift = k / fact[i];
        int c = -1;
        while (shift >= 0) {
            shift -= !used[++c];
        }
        used[c] = true;

        int t = c - 13 + n;
        if (t > 0) {
            if (isLucky(n - i))
                ans += isLucky(t) - 1;
        }

        k %= fact[i];
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

static boolean[] used = new boolean[20];
static long[] fact = new long[20];

static int cntLucky(long a, long b) {
    if (a > b) return 0;
    return 1 + cntLucky(a * 10 + 4, b) + cntLucky(a * 10 + 7, b);
}

static boolean isLucky(long a) {
    if (a == 0) return true;
    long d = a % 10;
    return (d == 4 || d == 7) && isLucky(a / 10);
}

public static long countLuckyPositions(long n, long k) {

    k--;

    fact[0] = 1;
    for (int i = 1; i <= 13; i++)
        fact[i] = fact[i - 1] * i;

    if (n <= 13 && fact[(int)n] <= k)
        return -1;

    int ans = cntLucky(0, n) - 1;

    for (int i = 13; i >= 0; i--) {
        long shift = k / fact[i];
        int c = -1;
        while (shift >= 0) {
            shift -= used[++c] ? 0 : 1;
        }
        used[c] = true;

        int t = c - 13 + (int)n;
        if (t > 0) {
            if (isLucky(n - i))
                ans += isLucky(t) ? 0 : -1;
        }

        k %= fact[i];
    }

    return ans;
}


### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256
