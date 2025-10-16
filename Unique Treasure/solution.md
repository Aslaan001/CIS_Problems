## CPP

### SOLUTION

int firstUniqueTreasure(vector<int>& nums) {
    unordered_map<int, int> freq;
    for (int val : nums) freq[val]++;
    for (int i = 0; i < nums.size(); i++) {
        if (freq[nums[i]] == 1) return i;
    }
    return -1;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static int firstUniqueTreasure(int[] nums) {
    Map<Integer, Integer> freq = new HashMap<>();
    for (int val : nums) freq.put(val, freq.getOrDefault(val, 0) + 1);
    for (int i = 0; i < nums.length; i++) {
        if (freq.get(nums[i]) == 1) return i;
    }
    return -1;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

#include <stdlib.h>

int firstUniqueTreasure(int nums[], int n) {
    int *freq = (int*)calloc(n * 2 + 1, sizeof(int));
    for (int i = 0; i < n; i++) {
        if (nums[i] >= 0 && nums[i] <= 1000000) freq[nums[i]]++;
    }
    for (int i = 0; i < n; i++) {
        if (nums[i] >= 0 && nums[i] <= 1000000 && freq[nums[i]] == 1) {
            free(freq);
            return i;
        }
    }
    free(freq);
    return -1;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function firstUniqueTreasure(nums) {
    const freq = new Map();
    for (let val of nums) freq.set(val, (freq.get(val) || 0) + 1);
    for (let i = 0; i < nums.length; i++) {
        if (freq.get(nums[i]) === 1) return i;
    }
    return -1;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def firstUniqueTreasure(nums):
    from collections import Counter
    freq = Counter(nums)
    for i, val in enumerate(nums):
        if freq[val] == 1:
            return i
    return -1

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
