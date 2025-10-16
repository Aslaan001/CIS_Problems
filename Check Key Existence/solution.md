## CPP

### SOLUTION

bool checkKeyExists(vector<int>& nums, int key) {
    for (int num : nums) {
        if (num == key) return true;
    }
    return false;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static boolean checkKeyExists(int[] nums, int key) {
    for (int val : nums) {
        if (val == key) return true;
    }
    return false;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

#include <stdbool.h>

bool checkKeyExists(int nums[], int n, int key) {
    for (int i = 0; i < n; i++) {
        if (nums[i] == key) return true;
    }
    return false;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function checkKeyExists(nums, key) {
    return nums.includes(key);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def checkKeyExists(nums, key):
    return key in nums

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
