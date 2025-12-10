## CPP

### SOLUTION

long long minRequiredK(const vector<long long>& a, const vector<long long>& b) {

    int n = a.size(), m = b.size();

    vector<int> pref(n + 2, 0), suff(n + 3, 0);

    int j = 0;
    for (int i = 0; i < n; ++i) {
        if (j < m && a[i] >= b[j]) ++j;
        pref[i + 1] = j;
    }

    j = m - 1;
    for (int i = n - 1; i >= 0; --i) {
        if (j >= 0 && a[i] >= b[j]) {
            --j;
            suff[i + 1] = suff[i + 2] + 1;
        } else {
            suff[i + 1] = suff[i + 2];
        }
    }

    long long ans = LLONG_MAX;

    for (int i = 0; i <= n; ++i) {
        int matched = pref[i];

        if (matched == m) {
            ans = 0;
            break;
        }

        if (matched < m && suff[i + 1] >= m - (matched + 1)) {
            ans = min(ans, b[matched]);
        }
    }

    return (ans == LLONG_MAX ? -1 : ans);
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512



## JAVA

### SOLUTION

public static long minRequiredK(long[] a, long[] b) {

    int n = a.length;
    int m = b.length;

    int[] pref = new int[n + 2];
    int[] suff = new int[n + 3];

    int j = 0;
    for (int i = 0; i < n; i++) {
        if (j < m && a[i] >= b[j]) j++;
        pref[i + 1] = j;
    }

    j = m - 1;
    for (int i = n - 1; i >= 0; i--) {
        if (j >= 0 && a[i] >= b[j]) {
            j--;
            suff[i + 1] = suff[i + 2] + 1;
        } else {
            suff[i + 1] = suff[i + 2];
        }
    }

    long ans = Long.MAX_VALUE;

    for (int i = 0; i <= n; i++) {

        int matched = pref[i];

        if (matched == m) {
            ans = 0;
            break;
        }

        if (matched < m && suff[i + 1] >= m - (matched + 1)) {
            ans = Math.min(ans, b[matched]);
        }
    }

    return (ans == Long.MAX_VALUE ? -1 : ans);
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
