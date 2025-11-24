## CPP

### SOLUTION

long long countHarmonicSubarrays(vector<int>& nums, int k) {
    unordered_map<int,long long> mp;
    mp[0] = 1;
    long long pref = 0, ans = 0;

    for (int x : nums) {
        pref += x;
        int r = ((pref % k) + k) % k;
        ans += mp[r];
        mp[r]++;
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

public static long countHarmonicSubarrays(int[] nums, int k) {
    Map<Integer, Long> map = new HashMap<>();
    map.put(0, 1L);
    long pref = 0, ans = 0;

    for (int x : nums) {
        pref += x;
        int r = (int)(((pref % k) + k) % k);
        ans += map.getOrDefault(r, 0L);
        map.put(r, map.getOrDefault(r, 0L) + 1);
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

long long countHarmonicSubarrays(int nums[], int n, int k) {
    long long freq[k];
    for (int i = 0; i < k; i++) freq[i] = 0;

    freq[0] = 1;
    long long pref = 0, ans = 0;

    for (int i = 0; i < n; i++) {
        pref += nums[i];
        int r = ((pref % k) + k) % k;
        ans += freq[r];
        freq[r]++;
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

function countHarmonicSubarrays(nums, k) {
  const freq = new Map();
  freq.set(0, 1);

  let pref = 0, ans = 0;

  for (const x of nums) {
    pref += x;
    let r = ((pref % k) + k) % k;
    ans += (freq.get(r) || 0);
    freq.set(r, (freq.get(r) || 0) + 1);
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

def countHarmonicSubarrays(nums, k):
    freq = {0: 1}
    pref = 0
    ans = 0
    for x in nums:
        pref += x
        r = (pref % k + k) % k
        ans += freq.get(r, 0)
        freq[r] = freq.get(r, 0) + 1
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
