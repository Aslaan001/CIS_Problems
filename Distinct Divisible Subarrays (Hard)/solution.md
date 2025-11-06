## CPP

### SOLUTION

long long countDistinctDivisibleSubarrays(vector<int>& v, int k) {
    map<long long, long long> mp;
    int n = v.size();
    mp[0]++;
    long long sum = 0;
    long long cnt = 0;
    for (int i = 0; i < n;) {
        int j = i;
        long long sum2 = sum;
        while (j < n && v[j] == v[i]) {
            sum2 += (long long)v[j];
            sum2 %= k;
            cnt += mp[sum2 % k];
            j++;
        }
        j = i;
        while (i < n && v[j] == v[i]) {
            sum += v[j];
            sum %= k;
            mp[sum]++;
            i++;
        }
    }
    return cnt;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION


public static long countDistinctDivisibleSubarrays(int[] v, int k) {
        Map<Long, Long> mp = new HashMap<>();
        mp.put(0L, 1L);
        long sum = 0, cnt = 0;
        int n = v.length;
        int i = 0;
        while (i < n) {
            int j = i;
            long sum2 = sum;
            while (j < n && v[j] == v[i]) {
                sum2 += v[j];
                sum2 %= k;
                cnt += mp.getOrDefault(sum2 % k, 0L);
                j++;
            }
            j = i;
            while (i < n && v[j] == v[i]) {
                sum += v[j];
                sum %= k;
                mp.put(sum, mp.getOrDefault(sum, 0L) + 1);
                i++;
            }
        }
        return cnt;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

typedef struct Pair {
    long long key;
    long long val;
    struct Pair* next;
} Pair;

Pair* add(Pair* head, long long key) {
    Pair* curr = head;
    while (curr) {
        if (curr->key == key) {
            curr->val++;
            return head;
        }
        curr = curr->next;
    }
    Pair* node = (Pair*)malloc(sizeof(Pair));
    node->key = key;
    node->val = 1;
    node->next = head;
    return node;
}

long long find(Pair* head, long long key) {
    while (head) {
        if (head->key == key) return head->val;
        head = head->next;
    }
    return 0;
}

long long countDistinctDivisibleSubarrays(int* v, int n, int k) {
    Pair* mp = (Pair*)malloc(sizeof(Pair));
    mp->key = 0; mp->val = 1; mp->next = NULL;
    long long sum = 0, cnt = 0;
    for (int i = 0; i < n;) {
        int j = i;
        long long sum2 = sum;
        while (j < n && v[j] == v[i]) {
            sum2 = (sum2 + v[j]) % k;
            cnt += find(mp, sum2 % k);
            j++;
        }
        j = i;
        while (i < n && v[j] == v[i]) {
            sum = (sum + v[j]) % k;
            mp = add(mp, sum);
            i++;
        }
    }
    return cnt;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function countDistinctDivisibleSubarrays(v, k) {
  const K = BigInt(k);
  const mp = new Map();
  mp.set(0n, 1n);
  let sum = 0n, cnt = 0n;
  const n = v.length;
  let i = 0;

  while (i < n) {
    let j = i;
    let sum2 = sum;
    while (j < n && v[j] === v[i]) {
      sum2 = (sum2 + BigInt(v[j])) % K;
      if (sum2 < 0n) sum2 += K;
      const mod = sum2;
      cnt += mp.get(mod) || 0n;
      j++;
    }
    j = i;
    while (i < n && v[j] === v[i]) {
      sum = (sum + BigInt(v[j])) % K;
      if (sum < 0n) sum += K;
      mp.set(sum, (mp.get(sum) || 0n) + 1n);
      i++;
    }
  }
  return cnt <= Number.MAX_SAFE_INTEGER ? Number(cnt) : cnt.toString();
}


### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION


def count_distinct_divisible_subarrays(v, k):
    mp = defaultdict(int)
    mp[0] = 1
    n = len(v)
    s = 0
    cnt = 0
    i = 0

    while i < n:
        j = i
        s2 = s
        while j < n and v[j] == v[i]:
            s2 = (s2 + v[j]) % k
            s2 = (s2 + k) % k      
            cnt += mp[s2]
            j += 1

        j = i
        while i < n and v[j] == v[i]:
            s = (s + v[j]) % k
            s = (s + k) % k   
            mp[s] += 1
            i += 1

    return cnt


### METADATA

TimeLimit
1000

MemoryLimit
512
