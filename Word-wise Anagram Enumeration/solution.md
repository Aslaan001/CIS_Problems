## CPP

### SOLUTION

int countAnagrams(string s) {
    const int mod = 1e9 + 7;
    static long long fact[100005];
    fact[0] = 1;
    for (int i = 1; i <= 100000; i++)
        fact[i] = (fact[i - 1] * i) % mod;

    auto modpow = [&](long long a, long long b) {
        long long res = 1;
        while (b) {
            if (b & 1) res = (res * a) % mod;
            a = (a * a) % mod;
            b >>= 1;
        }
        return res;
    };

    auto inv = [&](long long x) {
        return modpow(x, mod - 2);
    };

    long long ans = 1;
    stringstream ss(s);
    string word;

    while (ss >> word) {
        int freq[26] = {0};
        for (char c : word) freq[c - 'a']++;
        long long ways = fact[word.size()];
        long long denom = 1;
        for (int i = 0; i < 26; i++)
            denom = (denom * fact[freq[i]]) % mod;
        ways = (ways * inv(denom)) % mod;
        ans = (ans * ways) % mod;
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

public static int countAnagrams(String s) {
    int mod = 1000000007;
    int MAX = 100000;
    long[] fact = new long[MAX + 1];
    fact[0] = 1;
    for (int i = 1; i <= MAX; i++) fact[i] = fact[i - 1] * i % mod;

    long ans = 1;
    String[] words = s.split(" ");

    for (String w : words) {
        int[] freq = new int[26];
        for (char c : w.toCharArray()) freq[c - 'a']++;
        long ways = fact[w.length()];
        long denom = 1;
        for (int i = 0; i < 26; i++)
            denom = denom * fact[freq[i]] % mod;
        ways = ways * modpow(denom, mod - 2, mod) % mod;
        ans = ans * ways % mod;
    }
    return (int)ans;
}

static long modpow(long a, long b, int mod) {
    long res = 1;
    while (b > 0) {
        if ((b & 1) == 1) res = res * a % mod;
        a = a * a % mod;
        b >>= 1;
    }
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int countAnagrams(char* s) {
    const int mod = 1000000007;
    static long long fact[100005];
    fact[0] = 1;
    for (int i = 1; i <= 100000; i++)
        fact[i] = (fact[i - 1] * i) % mod;

    long long ans = 1;
    char* token = strtok(s, " ");
    while (token) {
        int freq[26] = {0};
        int len = strlen(token);
        for (int i = 0; i < len; i++)
            freq[token[i] - 'a']++;

        long long ways = fact[len];
        long long denom = 1;
        for (int i = 0; i < 26; i++)
            denom = (denom * fact[freq[i]]) % mod;

        long long inv = 1, p = mod - 2, base = denom;
        while (p) {
            if (p & 1) inv = inv * base % mod;
            base = base * base % mod;
            p >>= 1;
        }

        ways = ways * inv % mod;
        ans = ans * ways % mod;
        token = strtok(NULL, " ");
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

function countAnagrams(s) {
    const mod = 1000000007;
    const MAX = 100000;
    const fact = Array(MAX + 1).fill(1);
    for (let i = 1; i <= MAX; i++) fact[i] = fact[i - 1] * i % mod;

    function modpow(a, b) {
        let res = 1;
        while (b > 0) {
            if (b & 1) res = res * a % mod;
            a = a * a % mod;
            b >>= 1;
        }
        return res;
    }

    let ans = 1;
    const words = s.split(" ");
    for (const w of words) {
        const freq = Array(26).fill(0);
        for (const c of w) freq[c.charCodeAt(0) - 97]++;
        let ways = fact[w.length];
        let denom = 1;
        for (let i = 0; i < 26; i++)
            denom = denom * fact[freq[i]] % mod;
        ways = ways * modpow(denom, mod - 2) % mod;
        ans = ans * ways % mod;
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def countAnagrams(s):
    mod = 10**9 + 7
    MAX = 100000
    fact = [1] * (MAX + 1)
    for i in range(1, MAX + 1):
        fact[i] = fact[i - 1] * i % mod

    def modpow(a, b):
        res = 1
        while b:
            if b & 1:
                res = res * a % mod
            a = a * a % mod
            b >>= 1
        return res

    ans = 1
    for word in s.split():
        freq = [0] * 26
        for c in word:
            freq[ord(c) - 97] += 1
        ways = fact[len(word)]
        denom = 1
        for f in freq:
            denom = denom * fact[f] % mod
        ways = ways * modpow(denom, mod - 2) % mod
        ans = ans * ways % mod
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
