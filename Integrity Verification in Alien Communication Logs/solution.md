## CPP

### SOLUTION

long long countSemiPrimeLCMPairs(int n, const vector<int>& a) {

    static int spf[200001];
    static bool initialized = false;

    if (!initialized) {
        for (int i = 2; i <= 200000; i++) {
            if (spf[i] == 0) {
                for (int j = i; j <= 200000; j += i)
                    if (spf[j] == 0) spf[j] = i;
            }
        }
        initialized = true;
    }

    unordered_map<int, long long> cnt;
    for (int x : a) cnt[x]++;

    long long ans = 0;
    long long primes = 0;

    for (auto &[x, c] : cnt) {
        int p = spf[x];

        if (x == p) {
            primes += c;
            ans -= c * (c - 1) / 2;
        } else {
            int q = x / p;
            if (spf[q] == q) {
                long long add = c * (c + 1) / 2;
                add += c * cnt[p];
                if (p != q) add += c * cnt[q];
                ans += add;
            }
        }
    }

    ans += primes * (primes - 1) / 2;
    return ans;
}

### METADATA

**TimeLimit**  
2000

**MemoryLimit** 
256



## JAVA

### SOLUTION

static int MAX = 200000;
static int[] spf = new int[MAX + 1];
static boolean initialized = false;

static void initSieve() {
    if (initialized) return;
    for (int i = 2; i <= MAX; i++) {
        if (spf[i] == 0) {
            for (int j = i; j <= MAX; j += i) {
                if (spf[j] == 0) spf[j] = i;
            }
        }
    }
    initialized = true;
}

public static long countSemiPrimeLCMPairs(int n, int[] a) {

    initSieve();

    HashMap<Integer, Long> cnt = new HashMap<>();
    for (int x : a)
        cnt.put(x, cnt.getOrDefault(x, 0L) + 1);

    long ans = 0;
    long primes = 0;

    for (Map.Entry<Integer, Long> e : cnt.entrySet()) {
        int x = e.getKey();
        long c = e.getValue();

        int p = spf[x];

        if (x == p) {
            primes += c;
            ans -= c * (c - 1) / 2;
        } else {
            int q = x / p;
            if (spf[q] == q) {
                long add = c * (c + 1) / 2;
                add += c * cnt.getOrDefault(p, 0L);
                if (p != q) add += c * cnt.getOrDefault(q, 0L);
                ans += add;
            }
        }
    }

    ans += primes * (primes - 1) / 2;
    return ans;
}

### METADATA

**TimeLimit**  
2000

**MemoryLimit** 
256
