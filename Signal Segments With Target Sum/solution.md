## CPP

### SOLUTION

int subarraySum(vector<int>& nums, int k) {
    unordered_map<long long, int> freq;
    freq[0] = 1;
    long long pref = 0;
    int ans = 0;
    for (int x : nums) {
        pref += x;
        if (freq.count(pref - k)) ans += freq[pref - k];
        freq[pref]++;
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

public static int subarraySum(int[] nums, int k) {
    Map<Integer, Integer> map = new HashMap<>();
    map.put(0, 1);
    int pref = 0, ans = 0;
    for (int x : nums) {
        pref += x;
        if (map.containsKey(pref - k)) ans += map.get(pref - k);
        map.put(pref, map.getOrDefault(pref, 0) + 1);
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

int subarraySum(int nums[], int n, int k) {
    int OFFSET = 20000000;
    int SIZE = 40000010;
    int* freq = calloc(SIZE, sizeof(int));
    long long pref = 0;
    int ans = 0;
    freq[OFFSET] = 1;
    for (int i = 0; i < n; i++) {
        pref += nums[i];
        long long need = pref - k;
        if (need + OFFSET >= 0 && need + OFFSET < SIZE)
            ans += freq[need + OFFSET];
        freq[pref + OFFSET]++;
    }
    free(freq);
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function subarraySum(nums, k) {
  const map = new Map();
  map.set(0, 1);
  let pref = 0, ans = 0;
  for (const x of nums) {
    pref += x;
    if (map.has(pref - k)) ans += map.get(pref - k);
    map.set(pref, (map.get(pref) || 0) + 1);
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

def subarraySum(nums, k):
    freq = {0: 1}
    pref = 0
    ans = 0
    for x in nums:
        pref += x
        if pref - k in freq:
            ans += freq[pref - k]
        freq[pref] = freq.get(pref, 0) + 1
    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
