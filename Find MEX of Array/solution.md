## CPP

### SOLUTION

int findMEX(vector<int>& nums) {
    unordered_set<int> s(nums.begin(), nums.end());
    int mex = 0;
    while (s.count(mex)) mex++;
    return mex;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static int findMEX(int[] nums) {
    HashSet<Integer> set = new HashSet<>();
    for (int val : nums) set.add(val);
    int mex = 0;
    while (set.contains(mex)) mex++;
    return mex;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

#include <stdbool.h>

int findMEX(int nums[], int n) {
    bool present[n + 2]; // enough to cover MEX
    for (int i = 0; i <= n + 1; i++) present[i] = false;
    for (int i = 0; i < n; i++) {
        if (nums[i] <= n) present[nums[i]] = true;
    }
    for (int i = 0; i <= n + 1; i++) {
        if (!present[i]) return i;
    }
    return n + 1;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function findMEX(nums) {
    let s = new Set(nums);
    let mex = 0;
    while (s.has(mex)) mex++;
    return mex;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def findMEX(nums):
    s = set(nums)
    mex = 0
    while mex in s:
        mex += 1
    return mex

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
