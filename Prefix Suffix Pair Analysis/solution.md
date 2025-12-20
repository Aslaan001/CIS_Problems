## CPP

### SOLUTION

long long countPrefixSuffixPairs(vector<string>& words) {
    using ll = long long;
    unordered_map<ll, ll> freq;
    ll ans = 0;
    const ll mod = (ll)1e17 + 3;

    for (auto &w : words) {
        ll l_hash = 0, r_hash = 0, power = 1;
        int n = w.size();

        for (int i = 1; i <= n; i++) {
            l_hash = (l_hash * 27 + (w[i - 1] - 'a' + 1)) % mod;
            r_hash = ((w[n - i] - 'a' + 1) * power + r_hash) % mod;
            power = (power * 27) % mod;

            if (l_hash == r_hash) {
                ans += freq[l_hash];
            }
        }
        freq[l_hash]++;
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static long countPrefixSuffixPairs(String[] words) {
    long mod = (long)1e17 + 3;
    HashMap<Long, Long> freq = new HashMap<>();
    long ans = 0;

    for (String w : words) {
        long lHash = 0, rHash = 0, power = 1;
        int n = w.length();

        for (int i = 1; i <= n; i++) {
            lHash = (lHash * 27 + (w.charAt(i - 1) - 'a' + 1)) % mod;
            rHash = ((w.charAt(n - i) - 'a' + 1) * power + rHash) % mod;
            power = (power * 27) % mod;

            if (lHash == rHash) {
                ans += freq.getOrDefault(lHash, 0L);
            }
        }
        freq.put(lHash, freq.getOrDefault(lHash, 0L) + 1);
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

long long countPrefixSuffixPairs(char words[][100005], int n) {
    typedef long long ll;
    const ll mod = (ll)1e17 + 3;
    ll ans = 0;

    static ll keys[500005];
    static ll vals[500005];
    int sz = 0;

    for (int idx = 0; idx < n; idx++) {
        char* w = words[idx];
        int len = strlen(w);
        ll l_hash = 0, r_hash = 0, power = 1;

        for (int i = 1; i <= len; i++) {
            l_hash = (l_hash * 27 + (w[i - 1] - 'a' + 1)) % mod;
            r_hash = ((w[len - i] - 'a' + 1) * power + r_hash) % mod;
            power = (power * 27) % mod;

            if (l_hash == r_hash) {
                for (int j = 0; j < sz; j++) {
                    if (keys[j] == l_hash) {
                        ans += vals[j];
                        break;
                    }
                }
            }
        }

        int found = 0;
        for (int j = 0; j < sz; j++) {
            if (keys[j] == l_hash) {
                vals[j]++;
                found = 1;
                break;
            }
        }
        if (!found) {
            keys[sz] = l_hash;
            vals[sz] = 1;
            sz++;
        }
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function countPrefixSuffixPairs(words) {
    const mod = BigInt("100000000000000003");
    const freq = new Map();
    let ans = 0n;

    for (const w of words) {
        let lHash = 0n, rHash = 0n, power = 1n;
        const n = w.length;

        for (let i = 1; i <= n; i++) {
            lHash = (lHash * 27n + BigInt(w.charCodeAt(i - 1) - 96)) % mod;
            rHash = (BigInt(w.charCodeAt(n - i) - 96) * power + rHash) % mod;
            power = (power * 27n) % mod;

            if (lHash === rHash && freq.has(lHash)) {
                ans += freq.get(lHash);
            }
        }
        freq.set(lHash, (freq.get(lHash) || 0n) + 1n);
    }
    return Number(ans);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def countPrefixSuffixPairs(words):
    mod = 10**17 + 3
    freq = {}
    ans = 0

    for w in words:
        l_hash = r_hash = 0
        power = 1
        n = len(w)

        for i in range(1, n + 1):
            l_hash = (l_hash * 27 + (ord(w[i - 1]) - 96)) % mod
            r_hash = ((ord(w[n - i]) - 96) * power + r_hash) % mod
            power = (power * 27) % mod

            if l_hash == r_hash:
                ans += freq.get(l_hash, 0)

        freq[l_hash] = freq.get(l_hash, 0) + 1

    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
