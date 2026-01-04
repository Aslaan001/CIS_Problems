## CPP

### SOLUTION

vector<bool> sieve(long long n) {
    vector<bool> v1(n + 1, true);
    v1[0] = v1[1] = false;

    for (long long i = 2; i * i <= n; ++i) {
        if (v1[i]) {
            for (long long j = i * i; j <= n; j += i) {
                v1[j] = false;
            }
        }
    }
    return v1;
}

long long countRangeCompliantSubarrays(vector<int>& nums, int k) {
    vector<bool> isPrime = sieve(100000);

    int i = 0, j = 0;
    long long ans = 0;

    multiset<int> primes;
    int prevPrimeIdx = -1;
    int lastPrimeIdx = -1;

    while (j < nums.size()) {

        if (isPrime[nums[j]]) {
            primes.insert(nums[j]);
            prevPrimeIdx = lastPrimeIdx;
            lastPrimeIdx = j;
        }

        while (primes.size() > 1 && (*primes.rbegin() - *primes.begin()) > k) {
            if (isPrime[nums[i]]) {
                primes.erase(primes.find(nums[i]));
            }
            i++;
        }

        if (primes.size() >= 2) {
            ans += (prevPrimeIdx - i + 1);
        }

        j++;
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

static boolean[] sieve(int n) {
    boolean[] isPrime = new boolean[n + 1];
    Arrays.fill(isPrime, true);
    isPrime[0] = isPrime[1] = false;

    for (int i = 2; i * i <= n; i++) {
        if (isPrime[i]) {
            for (int j = i * i; j <= n; j += i) {
                isPrime[j] = false;
            }
        }
    }
    return isPrime;
}

public static long countRangeCompliantSubarrays(int[] nums, int k) {
    boolean[] isPrime = sieve(100000);

    int i = 0, j = 0;
    long ans = 0;

    TreeMap<Integer, Integer> map = new TreeMap<>();
    int prevPrimeIdx = -1;
    int lastPrimeIdx = -1;

    while (j < nums.length) {

        if (isPrime[nums[j]]) {
            map.put(nums[j], map.getOrDefault(nums[j], 0) + 1);
            prevPrimeIdx = lastPrimeIdx;
            lastPrimeIdx = j;
        }

        while (map.size() > 1 && map.lastKey() - map.firstKey() > k) {
            if (isPrime[nums[i]]) {
                int val = nums[i];
                map.put(val, map.get(val) - 1);
                if (map.get(val) == 0) map.remove(val);
            }
            i++;
        }

        if (map.size() >= 2) {
            ans += (prevPrimeIdx - i + 1);
        }

        j++;
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

long long countRangeCompliantSubarrays(int* nums, int n, int k) {
    int MAX = 100000;
    int isPrime[MAX + 1];
    for (int i = 0; i <= MAX; i++) isPrime[i] = 1;
    isPrime[0] = isPrime[1] = 0;

    for (int i = 2; i * i <= MAX; i++) {
        if (isPrime[i]) {
            for (int j = i * i; j <= MAX; j += i)
                isPrime[j] = 0;
        }
    }

    int freq[MAX + 1] = {0};
    int i = 0, j = 0;
    long long ans = 0;
    int minv = MAX, maxv = 0;
    int primeCount = 0;
    int prevPrimeIdx = -1, lastPrimeIdx = -1;

    while (j < n) {

        if (isPrime[nums[j]]) {
            freq[nums[j]]++;
            primeCount++;
            if (nums[j] < minv) minv = nums[j];
            if (nums[j] > maxv) maxv = nums[j];
            prevPrimeIdx = lastPrimeIdx;
            lastPrimeIdx = j;
        }

        while (primeCount > 1 && maxv - minv > k) {
            if (isPrime[nums[i]]) {
                freq[nums[i]]--;
                if (freq[nums[i]] == 0) {
                    primeCount--;
                    if (nums[i] == minv)
                        while (minv <= MAX && freq[minv] == 0) minv++;
                    if (nums[i] == maxv)
                        while (maxv >= 0 && freq[maxv] == 0) maxv--;
                }
            }
            i++;
        }

        if (primeCount >= 2) {
            ans += (prevPrimeIdx - i + 1);
        }

        j++;
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

function countRangeCompliantSubarrays(nums, k) {
    const MAX = 100000;
    const isPrime = Array(MAX + 1).fill(true);
    isPrime[0] = isPrime[1] = false;

    for (let i = 2; i * i <= MAX; i++) {
        if (isPrime[i]) {
            for (let j = i * i; j <= MAX; j += i)
                isPrime[j] = false;
        }
    }

    let i = 0, j = 0;
    let ans = 0;
    let map = new Map();
    let prevPrimeIdx = -1, lastPrimeIdx = -1;

    const getMinMax = () => {
        let mn = Infinity, mx = -Infinity;
        for (let key of map.keys()) {
            mn = Math.min(mn, key);
            mx = Math.max(mx, key);
        }
        return [mn, mx];
    };

    while (j < nums.length) {

        if (isPrime[nums[j]]) {
            map.set(nums[j], (map.get(nums[j]) || 0) + 1);
            prevPrimeIdx = lastPrimeIdx;
            lastPrimeIdx = j;
        }

        while (map.size > 1) {
            let [mn, mx] = getMinMax();
            if (mx - mn <= k) break;

            if (isPrime[nums[i]]) {
                map.set(nums[i], map.get(nums[i]) - 1);
                if (map.get(nums[i]) === 0) map.delete(nums[i]);
            }
            i++;
        }

        if (map.size >= 2) {
            ans += (prevPrimeIdx - i + 1);
        }

        j++;
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

def count_range_compliant_subarrays(nums, k):
    MAX = 100000
    is_prime = [True] * (MAX + 1)
    is_prime[0] = is_prime[1] = False

    for i in range(2, int(MAX ** 0.5) + 1):
        if is_prime[i]:
            for j in range(i * i, MAX + 1, i):
                is_prime[j] = False

    i = j = 0
    ans = 0
    from collections import Counter
    freq = Counter()
    prev_prime_idx = -1
    last_prime_idx = -1

    while j < len(nums):

        if is_prime[nums[j]]:
            freq[nums[j]] += 1
            prev_prime_idx = last_prime_idx
            last_prime_idx = j

        while len(freq) > 1 and max(freq) - min(freq) > k:
            if is_prime[nums[i]]:
                freq[nums[i]] -= 1
                if freq[nums[i]] == 0:
                    del freq[nums[i]]
            i += 1

        if len(freq) >= 2:
            ans += (prev_prime_idx - i + 1)

        j += 1

    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
