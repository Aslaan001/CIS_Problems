## CPP

### SOLUTION

long long minClusterCost(int n, const vector<long long>& p) {

    vector<long long> gc1(n), gc2(n);

    gc1[0] = p[0];
    for (int i = 1; i < n; i++)
        gc1[i] = std::gcd(gc1[i - 1], p[i]);
    gc2[n - 1] = p[n - 1];
    for (int i = n - 2; i >= 0; i--)
        gc2[i] = std::gcd(gc2[i + 1], p[i]);

    long long res = gc2[0];

    for (int i = 1; i < n - 1; i++)
        res += min(gc1[i], gc2[i]);

    return res;
}


### METADATA

**TimeLimit**  
3000

**MemoryLimit**  
1024



## JAVA

### SOLUTION

static long gcd(long a, long b) {
        while (b != 0) {
            long t = a % b;
            a = b;
            b = t;
        }
        return a;
    }

    public static long minClusterCost(int n, long[] p) {

        long[] gc1 = new long[n];
        long[] gc2 = new long[n];

        gc1[0] = p[0];
        for (int i = 1; i < n; i++) {
            gc1[i] = gcd(gc1[i - 1], p[i]);
        }

        gc2[n - 1] = p[n - 1];
        for (int i = n - 2; i >= 0; i--) {
            gc2[i] = gcd(gc2[i + 1], p[i]);
        }

        long res = gc2[0];
        for (int i = 1; i < n - 1; i++) {
            res += Math.min(gc1[i], gc2[i]);
        }

        return res;
}



### METADATA

**TimeLimit**  
3000

**MemoryLimit**  
1024
