## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

long long kDivisibleLengthMaximumSubarraySum(vector<int>& nums, int k) {
    const long long INF = 1e18;
    int n = nums.size();
    long long ans = -INF;
    vector<long long> minPrefix(k, INF);
    long long prefix = 0;
    minPrefix[0] = 0;

    for (int i = 0; i < n; i++) {
        prefix += nums[i];
        int r = (i + 1) % k;
        if (minPrefix[r] != INF) {
            ans = max(ans, prefix - minPrefix[r]);
        }
        minPrefix[r] = min(minPrefix[r], prefix);
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

public static long kDivisibleLengthMaximumSubarraySum(int[] nums, int k) {
    long INF = (long)1e18;
    long[] minPrefix = new long[k];
    Arrays.fill(minPrefix, INF);
    minPrefix[0] = 0;
    long prefix = 0;
    long ans = -INF;

    for (int i = 0; i < nums.length; i++) {
        prefix += nums[i];
        int r = (i + 1) % k;
        if (minPrefix[r] != INF) {
            ans = Math.max(ans, prefix - minPrefix[r]);
        }
        minPrefix[r] = Math.min(minPrefix[r], prefix);
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

#include <stdio.h>
#include <limits.h>

long long kDivisibleLengthMaximumSubarraySum(int* nums, int n, int k) {
    const long long INF = 1000000000000000000LL;
    long long minPrefix[k];
    for (int i = 0; i < k; i++) minPrefix[i] = INF;
    minPrefix[0] = 0;
    long long prefix = 0, ans = -INF;

    for (int i = 0; i < n; i++) {
        prefix += nums[i];
        int r = (i + 1) % k;
        if (minPrefix[r] != INF) {
            long long val = prefix - minPrefix[r];
            if (val > ans) ans = val;
        }
        if (prefix < minPrefix[r]) minPrefix[r] = prefix;
    }
    return ans;
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  



## JAVASCRIPT

### SOLUTION

function kDivisibleLengthMaximumSubarraySum(nums, k) {
  const INF = 10n ** 18n;
  const minPrefix = Array(k).fill(INF);
  minPrefix[0] = 0n;
  let prefix = 0n;
  let ans = -INF;

  for (let i = 0; i < nums.length; i++) {
    prefix += BigInt(nums[i]);
    const r = BigInt((i + 1) % k);
    if (minPrefix[Number(r)] !== INF) {
      ans = ans > prefix - minPrefix[Number(r)] ? ans : prefix - minPrefix[Number(r)];
    }
    if (prefix < minPrefix[Number(r)]) minPrefix[Number(r)] = prefix;
  }
  return ans.toString();
}

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  



## PYTHON

### SOLUTION

def k_divisible_length_maximum_subarray_sum(nums, k):
    INF = 10**18
    min_prefix = [INF] * k
    min_prefix[0] = 0
    prefix = 0
    ans = -INF

    for i, x in enumerate(nums, 1):
        prefix += x
        r = i % k
        ans = max(ans, prefix - min_prefix[r])
        min_prefix[r] = min(min_prefix[r], prefix)

    return ans

### METADATA

TimeLimit  
1000  

MemoryLimit  
512  
