## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int maximumSmoothSubarrayWithOneChange(vector<int>& nums) {
    int n = nums.size();
    if (n <= 2) return n;

    vector<int> left(n, 1), right(n, 1);

    for (int i = 1; i < n; i++) {
        if (nums[i] >= nums[i - 1])
            left[i] = left[i - 1] + 1;
    }

    for (int i = n - 2; i >= 0; i--) {
        if (nums[i] <= nums[i + 1])
            right[i] = right[i + 1] + 1;
    }

    int ans = max(left[n-1], right[0]);

    for (int i = 1; i < n - 1; i++) {
        if (nums[i + 1] >= nums[i - 1]) {
            ans = max(ans, left[i - 1] + 1 + right[i + 1]);
        } else {
            ans = max(ans, max(left[i], right[i]) + 1);
        }
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

public static int maximumSmoothSubarrayWithOneChange(int[] nums) {
    int n = nums.length;
    if (n <= 2) return n;

    int[] left = new int[n];
    int[] right = new int[n];
    Arrays.fill(left, 1);
    Arrays.fill(right, 1);

    for (int i = 1; i < n; i++) {
        if (nums[i] >= nums[i - 1])
            left[i] = left[i - 1] + 1;
    }

    for (int i = n - 2; i >= 0; i--) {
        if (nums[i] <= nums[i + 1])
            right[i] = right[i + 1] + 1;
    }

    int ans = Math.max(left[n-1], right[0]);

    for (int i = 1; i < n - 1; i++) {
        if (nums[i + 1] >= nums[i - 1])
            ans = Math.max(ans, left[i - 1] + 1 + right[i + 1]);
        else
            ans = Math.max(ans, Math.max(left[i], right[i]) + 1);
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
#include <stdlib.h>

int maximumSmoothSubarrayWithOneChange(int* nums, int n) {
    if (n <= 2) return n;

    int left[n], right[n];
    for (int i = 0; i < n; i++) left[i] = right[i] = 1;

    for (int i = 1; i < n; i++)
        if (nums[i] >= nums[i - 1])
            left[i] = left[i - 1] + 1;

    for (int i = n - 2; i >= 0; i--)
        if (nums[i] <= nums[i + 1])
            right[i] = right[i + 1] + 1;

    int ans = left[n-1] > right[0] ? left[n-1] : right[0];

    for (int i = 1; i < n - 1; i++) {
        if (nums[i + 1] >= nums[i - 1]) {
            int temp = left[i - 1] + 1 + right[i + 1];
            if (temp > ans) ans = temp;
        } else {
            int temp1 = left[i] + 1;
            int temp2 = right[i] + 1;
            if (temp1 > ans) ans = temp1;
            if (temp2 > ans) ans = temp2;
        }
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

function maximumSmoothSubarrayWithOneChange(nums) {
  const n = nums.length;
  if (n <= 2) return n;

  const left = Array(n).fill(1);
  const right = Array(n).fill(1);

  for (let i = 1; i < n; i++)
    if (nums[i] >= nums[i - 1]) left[i] = left[i - 1] + 1;

  for (let i = n - 2; i >= 0; i--)
    if (nums[i] <= nums[i + 1]) right[i] = right[i + 1] + 1;

  let ans = Math.max(left[n-1], right[0]);

  for (let i = 1; i < n - 1; i++) {
    if (nums[i + 1] >= nums[i - 1])
      ans = Math.max(ans, left[i - 1] + 1 + right[i + 1]);
    else
      ans = Math.max(ans, Math.max(left[i], right[i]) + 1);
  }

  return ans;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def maximum_smooth_subarray_with_one_change(nums):
    n = len(nums)
    if n <= 2:
        return n

    left = [1] * n
    right = [1] * n

    for i in range(1, n):
        if nums[i] >= nums[i - 1]:
            left[i] = left[i - 1] + 1

    for i in range(n - 2, -1, -1):
        if nums[i] <= nums[i + 1]:
            right[i] = right[i + 1] + 1

    ans = max(left[-1], right[0])

    for i in range(1, n - 1):
        if nums[i + 1] >= nums[i - 1]:
            ans = max(ans, left[i - 1] + 1 + right[i + 1])
        else:
            ans = max(ans, max(left[i], right[i]) + 1)

    return ans

### METADATA

TimeLimit  
1000

MemoryLimit  
512
