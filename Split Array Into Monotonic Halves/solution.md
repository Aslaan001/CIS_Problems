## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

long long minSplitDifference(vector<int>& nums) {
    int n = nums.size();
    vector<long long> v1(n, 0), v2(n, 0), pre;
    long long s = 0;
    for (int i = 0; i < nums.size(); i++) {
        s += nums[i];
        pre.push_back(s);
    }
    for (int i = 1; i < nums.size(); i++) {
        if (nums[i] > nums[i - 1]) v1[i] = 0;
        else v1[i] = 1;
    }
    for (int i = 1; i < nums.size(); i++) {
        v1[i] = v1[i] + v1[i - 1];
    }
    for (int i = n - 2; i >= 0; i--) {
        if (nums[i] > nums[i + 1]) v2[i] = 0;
        else v2[i] = 1;
    }
    for (int i = n - 2; i >= 0; i--) {
        v2[i] = v2[i] + v2[i + 1];
    }
    long long m = 1e15;
    for (int i = 0; i < v1.size() - 1; i++) {
        if (v1[i] == 0 && v2[i + 1] == 0) {
            long long kk = pre[i];
            long long ll = pre[n - 1] - pre[i];
            m = min(m, abs(ll - kk));
        }
    }
    if (m == 1e15) return -1;
    return m;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

public static long minSplitDifference(int[] nums) {
        int n = nums.length;
        long[] v1 = new long[n];
        long[] v2 = new long[n];
        long[] pre = new long[n];
        long s = 0;
        for (int i = 0; i < n; i++) {
            s += nums[i];
            pre[i] = s;
        }
        for (int i = 1; i < n; i++) {
            v1[i] = (nums[i] > nums[i - 1]) ? 0 : 1;
        }
        for (int i = 1; i < n; i++) {
            v1[i] += v1[i - 1];
        }
        for (int i = n - 2; i >= 0; i--) {
            v2[i] = (nums[i] > nums[i + 1]) ? 0 : 1;
        }
        for (int i = n - 2; i >= 0; i--) {
            v2[i] += v2[i + 1];
        }
        long m = (long) 1e15;
        for (int i = 0; i < n - 1; i++) {
            if (v1[i] == 0 && v2[i + 1] == 0) {
                long left = pre[i];
                long right = pre[n - 1] - pre[i];
                m = Math.min(m, Math.abs(right - left));
            }
        }
        return (m == (long) 1e15) ? -1 : m;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

#include <stdio.h>
#include <stdlib.h>
#include <math.h>

long long minSplitDifference(int* nums, int n) {
    long long* v1 = (long long*)calloc(n, sizeof(long long));
    long long* v2 = (long long*)calloc(n, sizeof(long long));
    long long* pre = (long long*)calloc(n, sizeof(long long));
    long long s = 0;
    for (int i = 0; i < n; i++) {
        s += nums[i];
        pre[i] = s;
    }
    for (int i = 1; i < n; i++) {
        v1[i] = (nums[i] > nums[i - 1]) ? 0 : 1;
    }
    for (int i = 1; i < n; i++) {
        v1[i] += v1[i - 1];
    }
    for (int i = n - 2; i >= 0; i--) {
        v2[i] = (nums[i] > nums[i + 1]) ? 0 : 1;
    }
    for (int i = n - 2; i >= 0; i--) {
        v2[i] += v2[i + 1];
    }
    long long m = 1000000000000000LL;
    for (int i = 0; i < n - 1; i++) {
        if (v1[i] == 0 && v2[i + 1] == 0) {
            long long left = pre[i];
            long long right = pre[n - 1] - pre[i];
            long long diff = llabs(right - left);
            if (diff < m) m = diff;
        }
    }
    free(v1);
    free(v2);
    free(pre);
    if (m == 1000000000000000LL) return -1;
    return m;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function minSplitDifference(nums) {
  const n = nums.length;
  const v1 = new Array(n).fill(0);
  const v2 = new Array(n).fill(0);
  const pre = new Array(n).fill(0);
  let s = 0n;
  for (let i = 0; i < n; i++) {
    s += BigInt(nums[i]);
    pre[i] = s;
  }
  for (let i = 1; i < n; i++) {
    v1[i] = nums[i] > nums[i - 1] ? 0 : 1;
  }
  for (let i = 1; i < n; i++) {
    v1[i] += v1[i - 1];
  }
  for (let i = n - 2; i >= 0; i--) {
    v2[i] = nums[i] > nums[i + 1] ? 0 : 1;
  }
  for (let i = n - 2; i >= 0; i--) {
    v2[i] += v2[i + 1];
  }
  let m = BigInt(1e15);
  for (let i = 0; i < n - 1; i++) {
    if (v1[i] === 0 && v2[i + 1] === 0) {
      const left = pre[i];
      const right = pre[n - 1] - pre[i];
      const diff = (left > right ? left - right : right - left);
      if (diff < m) m = diff;
    }
  }
  return m === BigInt(1e15) ? -1 : Number(m);
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def min_split_difference(nums):
    n = len(nums)
    v1 = [0] * n
    v2 = [0] * n
    pre = [0] * n
    s = 0
    for i in range(n):
        s += nums[i]
        pre[i] = s
    for i in range(1, n):
        v1[i] = 0 if nums[i] > nums[i - 1] else 1
    for i in range(1, n):
        v1[i] += v1[i - 1]
    for i in range(n - 2, -1, -1):
        v2[i] = 0 if nums[i] > nums[i + 1] else 1
    for i in range(n - 2, -1, -1):
        v2[i] += v2[i + 1]
    m = 10**15
    for i in range(n - 1):
        if v1[i] == 0 and v2[i + 1] == 0:
            left = pre[i]
            right = pre[n - 1] - pre[i]
            m = min(m, abs(right - left))
    return -1 if m == 10**15 else m

### METADATA

TimeLimit
1000

MemoryLimit
512
