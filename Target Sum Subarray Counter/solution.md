## CPP

### SOLUTION

long long countSubarraysWithSumK(vector<int>& nums, int k) {
    unordered_map<long long, long long> freq;
    freq[0] = 1;

    long long prefix = 0;
    long long ans = 0;

    for (int x : nums) {
        prefix += x;
        if (freq.count(prefix - k)) {
            ans += freq[prefix - k];
        }
        freq[prefix]++;
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

public static long countSubarraysWithSumK(int[] nums, int k) {
    HashMap<Long, Long> freq = new HashMap<>();
    freq.put(0L, 1L);

    long prefix = 0;
    long ans = 0;

    for (int x : nums) {
        prefix += x;
        if (freq.containsKey(prefix - k)) {
            ans += freq.get(prefix - k);
        }
        freq.put(prefix, freq.getOrDefault(prefix, 0L) + 1);
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

long long countSubarraysWithSumK(int* nums, int n, int k) {
    long long ans = 0, prefix = 0;

    // hash map using array with offset
    // value range: [-2e7, 2e7]
    static int freq[40000001];
    int OFFSET = 20000000;

    for (int i = 0; i < 40000001; i++) freq[i] = 0;
    freq[OFFSET] = 1;

    for (int i = 0; i < n; i++) {
        prefix += nums[i];
        ans += freq[prefix - k + OFFSET];
        freq[prefix + OFFSET]++;
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

function countSubarraysWithSumK(nums, k) {
  const freq = new Map();
  freq.set(0, 1);

  let prefix = 0;
  let ans = 0;

  for (const x of nums) {
    prefix += x;
    if (freq.has(prefix - k)) {
      ans += freq.get(prefix - k);
    }
    freq.set(prefix, (freq.get(prefix) || 0) + 1);
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

def count_subarrays_with_sum_k(nums, k):
    freq = {0: 1}
    prefix = 0
    ans = 0

    for x in nums:
        prefix += x
        ans += freq.get(prefix - k, 0)
        freq[prefix] = freq.get(prefix, 0) + 1

    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
