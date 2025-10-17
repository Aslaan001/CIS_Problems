## CPP

### SOLUTION

int twinRisingSubarrays(vector<int>& nums) {
    auto fun = [](vector<int>& nums, int k) {
        int n = nums.size();
        vector<int> v1(n, 0);
        for (int i = 1; i < n; i++) if (nums[i] > nums[i-1]) v1[i] = 1;
        for (int i = 1; i < n; i++) v1[i] += v1[i-1];
        for (int i = k-1; i < n-k; i++)
            if (v1[i] - v1[i-(k-1)] == k-1 && v1[i+k] - v1[i+1] == k-1) return true;
        return false;
    };

    int l = 1, h = nums.size(), ans = 0;
    while (l <= h) {
        int mid = (l+h)/2;
        if (fun(nums, mid)) { ans = mid; l = mid+1; }
        else h = mid-1;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  

---

## JAVA

### SOLUTION

public static int twinRisingSubarrays(int[] nums) {
    java.util.function.BiFunction<int[], Integer, Boolean> fun = (arr, k) -> {
        int n = arr.length;
        int[] v1 = new int[n];
        for (int i = 1; i < n; i++) if (arr[i] > arr[i-1]) v1[i] = 1;
        for (int i = 1; i < n; i++) v1[i] += v1[i-1];
        for (int i = k-1; i < n-k; i++)
            if (v1[i] - v1[i-(k-1)] == k-1 && v1[i+k] - v1[i+1] == k-1) return true;
        return false;
    };

    int l = 1, h = nums.length, ans = 0;
    while (l <= h) {
        int mid = (l+h)/2;
        if (fun.apply(nums, mid)) { ans = mid; l = mid+1; }
        else h = mid-1;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  

---

## C

### SOLUTION

#include <stdlib.h>
#include <stdbool.h>

bool fun(int nums[], int n, int k) {
    int* v1 = (int*)calloc(n, sizeof(int));
    for (int i = 1; i < n; i++) if (nums[i] > nums[i-1]) v1[i] = 1;
    for (int i = 1; i < n; i++) v1[i] += v1[i-1];
    for (int i = k-1; i < n-k; i++)
        if (v1[i] - v1[i-(k-1)] == k-1 && v1[i+k] - v1[i+1] == k-1) { free(v1); return true; }
    free(v1);
    return false;
}

int twinRisingSubarrays(int nums[], int n) {
    int l = 1, h = n, ans = 0;
    while (l <= h) {
        int mid = (l+h)/2;
        if (fun(nums, n, mid)) { ans = mid; l = mid+1; }
        else h = mid-1;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  

---

## JAVASCRIPT

### SOLUTION

function twinRisingSubarrays(nums) {
    const fun = (nums, k) => {
        const n = nums.length;
        const v1 = Array(n).fill(0);
        for (let i = 1; i < n; i++) if (nums[i] > nums[i-1]) v1[i] = 1;
        for (let i = 1; i < n; i++) v1[i] += v1[i-1];
        for (let i = k-1; i < n-k; i++)
            if (v1[i] - v1[i-(k-1)] === k-1 && v1[i+k] - v1[i+1] === k-1) return true;
        return false;
    };

    let l = 1, h = nums.length, ans = 0;
    while (l <= h) {
        const mid = Math.floor((l+h)/2);
        if (fun(nums, mid)) { ans = mid; l = mid+1; }
        else h = mid-1;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  

---

## PYTHON

### SOLUTION

def twinRisingSubarrays(nums):
    def fun(nums, k):
        n = len(nums)
        v1 = [0]*n
        for i in range(1, n):
            if nums[i] > nums[i-1]: v1[i] = 1
        for i in range(1, n): v1[i] += v1[i-1]
        for i in range(k-1, n-k):
            if v1[i] - v1[i-(k-1)] == k-1 and v1[i+k] - v1[i+1] == k-1: return True
        return False

    l, h, ans = 1, len(nums), 0
    while l <= h:
        mid = (l+h)//2
        if fun(nums, mid): ans = mid; l = mid+1
        else: h = mid-1
    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
