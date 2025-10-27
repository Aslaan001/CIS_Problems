## CPP

### SOLUTION

string arrayPairSumDivisible(vector<int>& arr, int k) {
    int n = arr.size();
    if (n % 2 != 0) return "NO";

    unordered_map<int, int> freq;
    for (int x : arr) {
        int rem = ((x % k) + k) % k;
        freq[rem]++;
    }

    for (auto& [r, count] : freq) {
        if (r == 0) {
            if (count % 2 != 0) return "NO";
        } else if (2 * r == k) {
            if (count % 2 != 0) return "NO";
        } else {
            if (freq[r] != freq[k - r]) return "NO";
        }
    }

    return "YES";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static String arrayPairSumDivisible(int[] arr, int k) {
    int n = arr.length;
    if (n % 2 != 0) return "NO";

    HashMap<Integer, Integer> freq = new HashMap<>();
    for (int x : arr) {
        int rem = ((x % k) + k) % k;
        freq.put(rem, freq.getOrDefault(rem, 0) + 1);
    }

    for (int r : freq.keySet()) {
        if (r == 0) {
            if (freq.get(r) % 2 != 0) return "NO";
        } else if (2 * r == k) {
            if (freq.get(r) % 2 != 0) return "NO";
        } else {
            if (!freq.get(r).equals(freq.getOrDefault(k - r, 0))) return "NO";
        }
    }

    return "YES";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

#include <stdbool.h>
#include <stdlib.h>

const bool arrayPairSumDivisible(int arr[], int n, int k) {
    if (n % 2 != 0) return 0;

    int* freq = (int*)calloc(k, sizeof(int));
    for (int i = 0; i < n; i++) {
        int rem = ((arr[i] % k) + k) % k;
        freq[rem]++;
    }

    for (int r = 0; r < k; r++) {
        if (r == 0) {
            if (freq[r] % 2 != 0) {
                free(freq);
                return 0;
            }
        } else if (2 * r == k) {
            if (freq[r] % 2 != 0) {
                free(freq);
                return 0;
            }
        } else {
            if (freq[r] != freq[k - r]) {
                free(freq);
                return 0;
            }
        }
    }

    free(freq);
    return 1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function arrayPairSumDivisible(arr, k) {
    if (arr.length % 2 !== 0) return "NO";

    const freq = new Map();
    for (const x of arr) {
        const rem = ((x % k) + k) % k;
        freq.set(rem, (freq.get(rem) || 0) + 1);
    }

    for (const [r, count] of freq.entries()) {
        if (r === 0) {
            if (count % 2 !== 0) return "NO";
        } else if (2 * r === k) {
            if (count % 2 !== 0) return "NO";
        } else {
            if (count !== (freq.get(k - r) || 0)) return "NO";
        }
    }

    return "YES";
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
        return "NO"

    freq = {}
    for x in arr:
        rem = ((x % k) + k) % k
        freq[rem] = freq.get(rem, 0) + 1

    for r, count in freq.items():
        if r == 0:
            if count % 2 != 0:
                return "NO"
        elif 2 * r == k:
            if count % 2 != 0:
                return "NO"
        else:
            if freq.get(k - r, 0) != count:
                return "NO"

    return "YES"

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
