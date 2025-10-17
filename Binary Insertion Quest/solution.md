## CPP

### SOLUTION

int binaryInsertionQuest(vector<int>& nums, int key) {
    int left = 0, right = nums.size();
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] < key) left = mid + 1;
        else right = mid;
    }
    return left; // position to insert key
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static int binaryInsertionQuest(int[] nums, int key) {
    int left = 0, right = nums.length;
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] < key) left = mid + 1;
        else right = mid;
    }
    return left; // position to insert key
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

#include <stdlib.h>

int binaryInsertionQuest(int nums[], int n, int key) {
    int left = 0, right = n;
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] < key) left = mid + 1;
        else right = mid;
    }
    return left; // position to insert key
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function binaryInsertionQuest(nums, key) {
    let left = 0, right = nums.length;
    while (left < right) {
        let mid = left + Math.floor((right - left) / 2);
        if (nums[mid] < key) left = mid + 1;
        else right = mid;
    }
    return left; // position to insert key
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def binaryInsertionQuest(nums, key):
    left, right = 0, len(nums)
    while left < right:
        mid = left + (right - left) // 2
        if nums[mid] < key:
            left = mid + 1
        else:
            right = mid
    return left  # position to insert key

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
