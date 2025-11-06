## CPP

### SOLUTION

int longestIncreasingStreak(vector<int>& nums) {
    int n = nums.size();
    int maxLength = 1, currentLength = 1;
    
    for (int i = 1; i < n; i++) {
        if (nums[i] > nums[i - 1]) {
            currentLength++;
            maxLength = max(maxLength, currentLength);
        } else {
            currentLength = 1;
        }
    }
    return maxLength;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

public static int longestIncreasingStreak(int[] nums) {
    int n = nums.length;
    int maxLength = 1, currentLength = 1;
    
    for (int i = 1; i < n; i++) {
        if (nums[i] > nums[i - 1]) {
            currentLength++;
            maxLength = Math.max(maxLength, currentLength);
        } else {
            currentLength = 1;
        }
    }
    return maxLength;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

#include <stdio.h>

int longestIncreasingStreak(int* nums, int n) {
    int maxLength = 1, currentLength = 1;
    
    for (int i = 1; i < n; i++) {
        if (nums[i] > nums[i - 1]) {
            currentLength++;
            maxLength = (maxLength > currentLength) ? maxLength : currentLength;
        } else {
            currentLength = 1;
        }
    }
    return maxLength;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function longestIncreasingStreak(nums) {
    let maxLength = 1, currentLength = 1;
    
    for (let i = 1; i < nums.length; i++) {
        if (nums[i] > nums[i - 1]) {
            currentLength++;
            maxLength = Math.max(maxLength, currentLength);
        } else {
            currentLength = 1;
        }
    }
    return maxLength;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def longest_increasing_streak(nums):
    max_length = 1
    current_length = 1
    
    for i in range(1, len(nums)):
        if nums[i] > nums[i - 1]:
            current_length += 1
            max_length = max(max_length, current_length)
        else:
            current_length = 1
    return max_length

### METADATA

TimeLimit
1000

MemoryLimit
512
