## CPP

### SOLUTION

int shortestSubarray(vector<int>& nums, long long k) {
    int n = nums.size();
    vector<long long> pref(n + 1, 0);
    for (int i = 0; i < n; i++) pref[i + 1] = pref[i] + nums[i];

    deque<int> dq;
    int ans = n + 1;

    for (int i = 0; i <= n; i++) {
        while (!dq.empty() && pref[i] - pref[dq.front()] >= k) {
            ans = min(ans, i - dq.front());
            dq.pop_front();
        }
        while (!dq.empty() && pref[i] <= pref[dq.back()]) {
            dq.pop_back();
        }
        dq.push_back(i);
    }

    return ans == n + 1 ? -1 : ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int shortestSubarray(int[] nums, long k) {
    int n = nums.length;
    long[] pref = new long[n + 1];
    for (int i = 0; i < n; i++) pref[i + 1] = pref[i] + nums[i];

    Deque<Integer> dq = new ArrayDeque<>();
    int ans = n + 1;

    for (int i = 0; i <= n; i++) {
        while (!dq.isEmpty() && pref[i] - pref[dq.peekFirst()] >= k) {
            ans = Math.min(ans, i - dq.pollFirst());
        }
        while (!dq.isEmpty() && pref[i] <= pref[dq.peekLast()]) {
            dq.pollLast();
        }
        dq.offerLast(i);
    }

    return ans == n + 1 ? -1 : ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int shortestSubarray(int nums[], int n, long long k) {
    long long pref[n + 1];
    pref[0] = 0;
    for (int i = 0; i < n; i++) pref[i + 1] = pref[i] + nums[i];

    int dq[n + 1];
    int front = 0, back = 0;
    int ans = n + 1;

    for (int i = 0; i <= n; i++) {
        while (front < back && pref[i] - pref[dq[front]] >= k) {
            int len = i - dq[front++];
            if (len < ans) ans = len;
        }
        while (front < back && pref[i] <= pref[dq[back - 1]]) {
            back--;
        }
        dq[back++] = i;
    }

    return ans == n + 1 ? -1 : ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function shortestSubarray(nums, k) {
    const n = nums.length;
    const pref = Array(n + 1).fill(0);
    for (let i = 0; i < n; i++) pref[i + 1] = pref[i] + nums[i];

    const dq = [];
    let ans = n + 1;

    for (let i = 0; i <= n; i++) {
        while (dq.length && pref[i] - pref[dq[0]] >= k) {
            ans = Math.min(ans, i - dq.shift());
        }
        while (dq.length && pref[i] <= pref[dq[dq.length - 1]]) {
            dq.pop();
        }
        dq.push(i);
    }

    return ans === n + 1 ? -1 : ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

from collections import deque

def shortest_subarray(nums, k):
    n = len(nums)
    pref = [0] * (n + 1)
    for i in range(n):
        pref[i + 1] = pref[i] + nums[i]

    dq = deque()
    ans = n + 1

    for i in range(n + 1):
        while dq and pref[i] - pref[dq[0]] >= k:
            ans = min(ans, i - dq.popleft())
        while dq and pref[i] <= pref[dq[-1]]:
            dq.pop()
        dq.append(i)

    return -1 if ans == n + 1 else ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
