## CPP

### SOLUTION

bool arrayPairSumDivisible(vector<int>& arr, int k) {
    int n = arr.size();
    if (n % 2 != 0) return false;

    unordered_map<int, int> freq;
    for (int x : arr) {
        int rem = ((x % k) + k) % k;
        freq[rem]++;
    }

    for (auto& [r, count] : freq) {
        if (r == 0) {
            if (count % 2 != 0) return false;
        } else if (2 * r == k) {
            if (count % 2 != 0) return false;
        } else {
            if (freq[r] != freq[k - r]) return false;
        }
    }

    return true;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static boolean arrayPairSumDivisible(int[] arr, int k) {
    int n = arr.length;
    if (n % 2 != 0) return false;

    HashMap<Integer, Integer> freq = new HashMap<>();
    for (int x : arr) {
        int rem = ((x % k) + k) % k;
        freq.put(rem, freq.getOrDefault(rem, 0) + 1);
    }

    for (int r : freq.keySet()) {
        if (r == 0) {
            if (freq.get(r) % 2 != 0) return false;
        } else if (2 * r == k) {
            if (freq.get(r) % 2 != 0) return false;
        } else {
            if (!freq.get(r).equals(freq.getOrDefault(k - r, 0))) return false;
        }
    }

    return true;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION


bool arrayPairSumDivisible(int arr[], int n, int k) {
    if (n % 2 != 0) return false;

    int* freq = (int*)calloc(k, sizeof(int));
    for (int i = 0; i < n; i++) {
        int rem = ((arr[i] % k) + k) % k;
        freq[rem]++;
    }

    for (int r = 0; r < k; r++) {
        if (r == 0) {
            if (freq[r] % 2 != 0) {
                free(freq);
                return false;
            }
        } else if (2 * r == k) {
            if (freq[r] % 2 != 0) {
                free(freq);
                return false;
            }
        } else {
            if (freq[r] != freq[k - r]) {
                free(freq);
                return false;
            }
        }
    }

    free(freq);
    return true;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function arrayPairSumDivisible(arr, k) {
    if (arr.length % 2 !== 0) return false;

    const freq = new Map();
    for (const x of arr) {
        const rem = ((x % k) + k) % k;
        freq.set(rem, (freq.get(rem) || 0) + 1);
    }

    for (const [r, count] of freq.entries()) {
        if (r === 0) {
            if (count % 2 !== 0) return false;
        } else if (2 * r === k) {
            if (count % 2 !== 0) return false;
        } else {
            if (count !== (freq.get(k - r) || 0)) return false;
        }
    }

    return true;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def arrayPairSumDivisible(arr, k):
    if len(arr) % 2 != 0:
        return False

    freq = {}
    for x in arr:
        rem = ((x % k) + k) % k
        freq[rem] = freq.get(rem, 0) + 1

    for r, count in freq.items():
        if r == 0:
            if count % 2 != 0:
                return False
        elif 2 * r == k:
            if count % 2 != 0:
                return False
        else:
            if freq.get(k - r, 0) != count:
                return False

    return True

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
