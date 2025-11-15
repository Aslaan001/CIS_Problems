## CPP

### SOLUTION

typedef long long ll;

long long balancedQuadrupleSubsequences(vector<int>& nums) {
    int n = nums.size();
    ll ans = 0;
    unordered_map<double, ll> f;
    vector<ll> cnt(1001, 0);
    for (int i = n - 1; i >= 6; i--) cnt[nums[i]] += 1;
    f[1.0 * nums[0] / nums[2]] += 1;
    for (int i = 4; i < n; i++) {
        for (int j = 1; j <= 1000; j++) {
            if (cnt[j] == 0) continue;
            double target = 1.0 * j / nums[i];
            ans += f[target] * cnt[j];
        }
        for (int j = i - 3; j >= 0; j--) {
            f[1.0 * nums[j] / nums[i - 1]] += 1;
        }
        if (i + 2 < n) cnt[nums[i + 2]] -= 1;
    }
    return ans;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  



## JAVA

### SOLUTION

public static long balancedQuadrupleSubsequences(int[] nums) {
    int n = nums.length;
    long ans = 0;
    Map<Double, Long> f = new HashMap<>();
    long[] cnt = new long[1001];
    for (int i = n - 1; i >= 6; i--) cnt[nums[i]]++;
    f.put(1.0 * nums[0] / nums[2], 1L);
    for (int i = 4; i < n; i++) {
        for (int j = 1; j <= 1000; j++) {
            if (cnt[j] == 0) continue;
            double target = 1.0 * j / nums[i];
            ans += f.getOrDefault(target, 0L) * cnt[j];
        }
        for (int j = i - 3; j >= 0; j--) {
            double ratio = 1.0 * nums[j] / nums[i - 1];
            f.put(ratio, f.getOrDefault(ratio, 0L) + 1L);
        }
        if (i + 2 < n) cnt[nums[i + 2]]--;
    }
    return ans;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  



## C

### SOLUTION

#include <math.h>
#include <stdlib.h>

long long balancedQuadrupleSubsequences(int* nums, int n) {
    long long ans = 0;
    double* keys = (double*)malloc(n * n * sizeof(double));
    long long* vals = (long long*)calloc(n * n, sizeof(long long));
    int ksize = 0;
    long long cnt[1001] = {0};
    for (int i = n - 1; i >= 6; i--) cnt[nums[i]]++;
    keys[ksize] = 1.0 * nums[0] / nums[2];
    vals[ksize++] = 1;
    for (int i = 4; i < n; i++) {
        for (int j = 1; j <= 1000; j++) {
            if (cnt[j] == 0) continue;
            double target = 1.0 * j / nums[i];
            for (int k = 0; k < ksize; k++) {
                if (fabs(keys[k] - target) < 1e-9) {
                    ans += vals[k] * cnt[j];
                    break;
                }
            }
        }
        for (int j = i - 3; j >= 0; j--) {
            double ratio = 1.0 * nums[j] / nums[i - 1];
            int found = 0;
            for (int k = 0; k < ksize; k++) {
                if (fabs(keys[k] - ratio) < 1e-9) {
                    vals[k]++;
                    found = 1;
                    break;
                }
            }
            if (!found) {
                keys[ksize] = ratio;
                vals[ksize++] = 1;
            }
        }
        if (i + 2 < n) cnt[nums[i + 2]]--;
    }
    free(keys);
    free(vals);
    return ans;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  



## JAVASCRIPT

### SOLUTION

function balancedQuadrupleSubsequences(nums) {
    const n = nums.length;
    let ans = 0n;
    const f = new Map();
    const cnt = new Array(1001).fill(0n);
    for (let i = n - 1; i >= 6; i--) cnt[nums[i]]++;
    f.set(nums[0] / nums[2], 1n);
    for (let i = 4; i < n; i++) {
        for (let j = 1; j <= 1000; j++) {
            if (cnt[j] === 0n) continue;
            const target = j / nums[i];
            if (f.has(target)) ans += f.get(target) * cnt[j];
        }
        for (let j = i - 3; j >= 0; j--) {
            const ratio = nums[j] / nums[i - 1];
            f.set(ratio, (f.get(ratio) || 0n) + 1n);
        }
        if (i + 2 < n) cnt[nums[i + 2]]--;
    }
    return Number(ans);
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  



## PYTHON

### SOLUTION

from collections import defaultdict

def balanced_quadruple_subsequences(nums):
    n = len(nums)
    if n < 7:
        return 0
    ans = 0
    f = defaultdict(int)         
    cnt = defaultdict(int)        

   
    for i in range(n - 1, 5, -1):
        cnt[nums[i]] += 1

    
    f[nums[0] / nums[2]] += 1

    for i in range(4, n):
        
        for val, c in cnt.items():
            if c == 0:
                continue
            target = val / nums[i]
            ans += f.get(target, 0) * c

        
        for j in range(i - 3, -1, -1):
            f[nums[j] / nums[i - 1]] += 1

        
        if i + 2 < n:
            v = nums[i + 2]
            cnt[v] -= 1
            if cnt[v] == 0:
                del cnt[v]

    return ans

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  
