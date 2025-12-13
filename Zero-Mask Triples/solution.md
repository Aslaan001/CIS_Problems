## CPP

### SOLUTION

int countZeroMaskTriples(vector<int>& nums) {
    unordered_map<int,int> mp;
    for (int a : nums)
        for (int b : nums)
            mp[a & b]++;

    long long cnt = 0;
    for (int a : nums)
        for (auto &p : mp)
            if ((p.first & a) == 0)
                cnt += p.second;

    return cnt;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static long countZeroMaskTriples(int[] nums) {
    HashMap<Integer, Integer> mp = new HashMap<>();

    for (int a : nums)
        for (int b : nums)
            mp.put(a & b, mp.getOrDefault(a & b, 0) + 1);

    long cnt = 0;
    for (int a : nums)
        for (var entry : mp.entrySet())
            if ((entry.getKey() & a) == 0)
                cnt += entry.getValue();

    return cnt;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

long long countZeroMaskTriples(int nums[], int n) {
    int maxmask = 1 << 16;
    int *freq = calloc(maxmask, sizeof(int));

    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            freq[ nums[i] & nums[j] ]++;

    long long cnt = 0;
    for (int i = 0; i < n; i++) {
        int a = nums[i];
        for (int mask = 0; mask < maxmask; mask++) {
            if ((mask & a) == 0)
                cnt += freq[mask];
        }
    }

    free(freq);
    return cnt;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function countZeroMaskTriples(nums) {
  const mp = new Map();

  for (let a of nums)
    for (let b of nums) {
      const k = a & b;
      mp.set(k, (mp.get(k) || 0) + 1);
    }

  let cnt = 0;
  for (let a of nums)
    for (let [mask, val] of mp)
      if ((mask & a) === 0)
        cnt += val;

  return cnt;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def countZeroMaskTriples(nums):
    from collections import defaultdict

    mp = defaultdict(int)
    for a in nums:
        for b in nums:
            mp[a & b] += 1

    cnt = 0
    for a in nums:
        for m, v in mp.items():
            if (m & a) == 0:
                cnt += v

    return cnt

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
