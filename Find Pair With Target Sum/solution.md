## CPP

### SOLUTION

pair<int,int> twoSum(vector<int>& nums, int target) {
    unordered_map<int,int> mp;
    for (int i = 0; i < nums.size(); i++) {
        int need = target - nums[i];
        if (mp.count(need)) {
            return {mp[need], i};
        }
        mp[nums[i]] = i;
    }
    return {-1, -1};
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int[] twoSum(int[] nums, int target) {
    HashMap<Integer, Integer> map = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
        int need = target - nums[i];
        if (map.containsKey(need)) {
            return new int[]{map.get(need), i};
        }
        map.put(nums[i], i);
    }
    return new int[]{-1, -1};
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int hashKey(int x) {
    return (x & 0x7fffffff) % 20011;
}

void twoSum(int nums[], int n, int target, int* a, int* b) {
    int key[20011], val[20011];
    for (int i = 0; i < 20011; i++) key[i] = 1e9;

    for (int i = 0; i < n; i++) {
        int need = target - nums[i];
        int h = hashKey(need);
        while (key[h] != 1e9) {
            if (key[h] == need) {
                *a = val[h];
                *b = i;
                return;
            }
            h = (h + 1) % 20011;
        }

        int h2 = hashKey(nums[i]);
        while (key[h2] != 1e9) h2 = (h2 + 1) % 20011;
        key[h2] = nums[i];
        val[h2] = i;
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function twoSum(nums, target) {
  const mp = new Map();
  for (let i = 0; i < nums.length; i++) {
    const need = target - nums[i];
    if (mp.has(need)) return [mp.get(need), i];
    mp.set(nums[i], i);
  }
  return [-1, -1];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def twoSum(nums, target):
    mp = {}
    for i, x in enumerate(nums):
        need = target - x
        if need in mp:
            return mp[need], i
        mp[x] = i
    return -1, -1

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
