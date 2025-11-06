## CPP

### SOLUTION

long long guardedSubarrays(vector<int>& nums) {
    int n = nums.size();
    vector<int> pre(n + 1, INT_MIN), suff(n + 1, INT_MIN);
    for (int i = 1; i <= n; i++) {
        pre[i] = max(pre[i - 1], nums[i - 1]);
    }
    for (int i = n - 1; i >= 0; i--) {
        suff[i] = max(suff[i + 1], nums[i]);
    }
    long long cnt = 0;
    for (int i = 0; i < n; i++) {
        if (pre[i] > nums[i] && i + 1 < n && suff[i + 1] > nums[i]) {
            cnt++;
        }
    }
    return cnt;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

public static long guardedSubarrays(int[] nums) {
    int n = nums.length;
    int[] pre = new int[n + 1];
    int[] suff = new int[n + 1];
    Arrays.fill(pre, Integer.MIN_VALUE);
    Arrays.fill(suff, Integer.MIN_VALUE);
    for (int i = 1; i <= n; i++) {
        pre[i] = Math.max(pre[i - 1], nums[i - 1]);
    }
    for (int i = n - 1; i >= 0; i--) {
        suff[i] = Math.max(suff[i + 1], nums[i]);
    }
    long cnt = 0;
    for (int i = 0; i < n; i++) {
        if (pre[i] > nums[i] && i + 1 < n && suff[i + 1] > nums[i]) {
            cnt++;
        }
    }
    return cnt;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

long long guardedSubarrays(int* nums, int n) {
    int pre[n + 1], suff[n + 1];
    for (int i = 0; i <= n; i++) {
        pre[i] = -2147483648;
        suff[i] = -2147483648;
    }
    for (int i = 1; i <= n; i++) {
        pre[i] = pre[i - 1] > nums[i - 1] ? pre[i - 1] : nums[i - 1];
    }
    for (int i = n - 1; i >= 0; i--) {
        suff[i] = suff[i + 1] > nums[i] ? suff[i + 1] : nums[i];
    }
    long long cnt = 0;
    for (int i = 0; i < n; i++) {
        if (pre[i] > nums[i] && i + 1 < n && suff[i + 1] > nums[i]) {
            cnt++;
        }
    }
    return cnt;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function guardedSubarrays(nums) {
    const n = nums.length;
    const pre = Array(n + 1).fill(-Infinity);
    const suff = Array(n + 1).fill(-Infinity);
    for (let i = 1; i <= n; i++) {
        pre[i] = Math.max(pre[i - 1], nums[i - 1]);
    }
    for (let i = n - 1; i >= 0; i--) {
        suff[i] = Math.max(suff[i + 1], nums[i]);
    }
    let cnt = 0n;
    for (let i = 0; i < n; i++) {
        if (pre[i] > nums[i] && i + 1 < n && suff[i + 1] > nums[i]) {
            cnt++;
        }
    }
    return Number(cnt);
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def guarded_subarrays(nums):
    n = len(nums)
    pre = [float('-inf')] * (n + 1)
    suff = [float('-inf')] * (n + 1)
    for i in range(1, n + 1):
        pre[i] = max(pre[i - 1], nums[i - 1])
    for i in range(n - 1, -1, -1):
        suff[i] = max(suff[i + 1], nums[i])
    cnt = 0
    for i in range(n):
        if pre[i] > nums[i] and i + 1 < n and suff[i + 1] > nums[i]:
            cnt += 1
    return cnt

### METADATA

TimeLimit
1000

MemoryLimit
512
