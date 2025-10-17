## CPP

### SOLUTION

int mysticSubarrayQuest(vector<int>& nums, int S) {
    int n = nums.size();
    int maxLen = 0, sum = 0, left = 0;

    for (int right = 0; right < n; right++) {
        sum += nums[right];
        while (sum > S && left <= right) {
            sum -= nums[left];
            left++;
        }
        maxLen = max(maxLen, right - left + 1);
    }

    return maxLen;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static int mysticSubarrayQuest(int[] nums, int S) {
    int n = nums.length;
    int maxLen = 0, sum = 0, left = 0;

    for (int right = 0; right < n; right++) {
        sum += nums[right];
        while (sum > S && left <= right) {
            sum -= nums[left];
            left++;
        }
        maxLen = Math.max(maxLen, right - left + 1);
    }

    return maxLen;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

#include <stdlib.h>

int mysticSubarrayQuest(int nums[], int n, int S) {
    int maxLen = 0, sum = 0, left = 0;

    for (int right = 0; right < n; right++) {
        sum += nums[right];
        while (sum > S && left <= right) {
            sum -= nums[left];
            left++;
        }
        if (right - left + 1 > maxLen)
            maxLen = right - left + 1;
    }

    return maxLen;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function mysticSubarrayQuest(nums, S) {
    let maxLen = 0, sum = 0, left = 0;
    for (let right = 0; right < nums.length; right++) {
        sum += nums[right];
        while (sum > S && left <= right) {
            sum -= nums[left];
            left++;
        }
        maxLen = Math.max(maxLen, right - left + 1);
    }
    return maxLen;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def mysticSubarrayQuest(nums, S):
    maxLen = 0
    sum_ = 0
    left = 0
    for right in range(len(nums)):
        sum_ += nums[right]
        while sum_ > S and left <= right:
            sum_ -= nums[left]
            left += 1
        maxLen = max(maxLen, right - left + 1)
    return maxLen

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
