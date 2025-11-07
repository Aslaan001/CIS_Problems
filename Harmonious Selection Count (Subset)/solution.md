## CPP

### SOLUTION


int countHarmoniousSubsets(vector<int>& nums, int k) {
    sort(nums.begin(), nums.end());
    unordered_map<int,int> freq, choose;
    for (int x : nums) freq[x]++;

    function<int(int)> solve = [&](int i) {
        if (i == nums.size()) return 1;
        int val = nums[i];
        int take = 0, notTake = 0;

        notTake = solve(i + freq[val]);

        if (choose[val - k] == 0) {
            choose[val]++;
            take = (solve(i + freq[val]) * ((int)pow(2, freq[val]) - 1));
            choose[val]--;
        }

        return take + notTake;
    };

    return solve(0) - 1;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int countHarmoniousSubsets(int[] nums, int k) {
    Arrays.sort(nums);
    Map<Integer, Integer> freq = new HashMap<>();
    Map<Integer, Integer> choose = new HashMap<>();
    for (int x : nums) freq.put(x, freq.getOrDefault(x, 0) + 1);
    List<Integer> unique = new ArrayList<>(freq.keySet());
    Collections.sort(unique);

    int sz = unique.size();

    java.util.function.Function<Integer, Integer> solve = new java.util.function.Function<>() {
        @Override
        public Integer apply(Integer idx) {
            if (idx == sz) return 1;
            int val = unique.get(idx);
            int count = freq.get(val);

            int ans = apply(idx + 1);

            if (!choose.containsKey(val - k) || choose.get(val - k) == 0) {
                choose.put(val, choose.getOrDefault(val, 0) + 1);
                ans += (int)(Math.pow(2, count) - 1) * apply(idx + 1);
                choose.put(val, choose.get(val) - 1);
            }

            return ans;
        }
    };

    return solve.apply(0) - 1;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION


int cmp(const void* a, const void* b) { return (*(int*)a - *(int*)b); }

int solve(int* nums, int* freq, int* uniq, int* choose, int sz, int idx, int k) {
    if (idx == sz) return 1;

    int val = uniq[idx];
    int count = freq[idx];

    int notTake = solve(nums, freq, uniq, choose, sz, idx + 1, k);

    int take = 0;
    int block = val - k;
    int ok = 1;
    for (int i = 0; i < sz; i++) {
        if (uniq[i] == block && choose[i] > 0) ok = 0;
    }
    if (ok) {
        choose[idx]++;
        take = ((1 << count) - 1) * solve(nums, freq, uniq, choose, sz, idx + 1, k);
        choose[idx]--;
    }

    return take + notTake;
}

int countHarmoniousSubsets(int nums[], int n, int k) {
    qsort(nums, n, sizeof(int), cmp);

    int uniq[18], freq[18], choose[18];
    memset(freq, 0, sizeof(freq));
    memset(choose, 0, sizeof(choose));
    int sz = 0;

    for (int i = 0; i < n; ) {
        int j = i;
        while (j < n && nums[j] == nums[i]) j++;
        uniq[sz] = nums[i];
        freq[sz] = j - i;
        sz++;
        i = j;
    }

    return solve(nums, freq, uniq, choose, sz, 0, k) - 1;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function countHarmoniousSubsets(nums, k) {
  nums.sort((a, b) => a - b);
  const freq = new Map();
  for (const x of nums) freq.set(x, (freq.get(x) || 0) + 1);
  const uniq = [...freq.keys()].sort((a, b) => a - b);
  const choose = new Map();
  
  function solve(i) {
    if (i === uniq.length) return 1;
    const val = uniq[i];
    const cnt = freq.get(val);

    let res = solve(i + 1);

    if (!choose.get(val - k)) {
      choose.set(val, (choose.get(val) || 0) + 1);
      res += (Math.pow(2, cnt) - 1) * solve(i + 1);
      choose.set(val, choose.get(val) - 1);
    }
    return res;
  }

  return solve(0) - 1;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def count_harmonious_subsets(nums, k):
    from collections import Counter

    nums.sort()
    freq = Counter(nums)
    unique = sorted(freq.keys())
    choose = Counter()

    def solve(i):
        if i == len(unique):
            return 1
        val = unique[i]
        cnt = freq[val]

        res = solve(i + 1)

        if choose[val - k] == 0:
            choose[val] += 1
            res += (2**cnt - 1) * solve(i + 1)
            choose[val] -= 1

        return res

    return solve(0) - 1

### METADATA

TimeLimit  
1000

MemoryLimit  
512
