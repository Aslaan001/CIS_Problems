## CPP

### SOLUTION

int mostFrequentElement(vector<int>& nums) {
    unordered_map<int, int> freq;
    for (int x : nums) freq[x]++;

    int ans = INT_MAX, best = 0;
    for (auto& [num, f] : freq) {
        if (f > best || (f == best && num < ans)) {
            best = f;
            ans = num;
        }
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

public static int mostFrequentElement(int[] nums) {
    Map<Integer, Integer> freq = new HashMap<>();
    for (int x : nums) {
        freq.put(x, freq.getOrDefault(x, 0) + 1);
    }

    int ans = Integer.MAX_VALUE, best = 0;
    for (int key : freq.keySet()) {
        int f = freq.get(key);
        if (f > best || (f == best && key < ans)) {
            best = f;
            ans = key;
        }
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

int mostFrequentElement(int nums[], int n) {
    int count[10001] = {0};
    for (int i = 0; i < n; i++) count[nums[i]]++;

    int best = 0, ans = 1e9;
    for (int i = 0; i < 10001; i++) {
        if (count[i] > 0) {
            if (count[i] > best || (count[i] == best && i < ans)) {
                best = count[i];
                ans = i;
            }
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

function mostFrequentElement(nums) {
  const freq = new Map();
  for (const x of nums) freq.set(x, (freq.get(x) || 0) + 1);

  let ans = Infinity, best = 0;
  for (const [num, f] of freq.entries()) {
    if (f > best || (f === best && num < ans)) {
      best = f;
      ans = num;
    }
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

def mostFrequentElement(nums):
    from collections import Counter
    freq = Counter(nums)
    best = 0
    ans = float('inf')
    for num, f in freq.items():
        if f > best or (f == best and num < ans):
            best = f
            ans = num
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
