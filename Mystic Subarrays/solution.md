## CPP

### SOLUTION

int mysticSubarrays(vector<int>& nums) {
    int n = nums.size(), count = 0;
    for (int i = 0; i < n; i++) {
        long long sum = 0, prod = 1;
        for (int j = i; j < n; j++) {
            sum += nums[j];
            prod *= nums[j];
            if (sum == prod) count++;
            if (prod > 1e9) break; // early stop to prevent overflow
        }
    }
    return count;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static int mysticSubarrays(int[] nums) {
    int n = nums.length, count = 0;
    for (int i = 0; i < n; i++) {
        long sum = 0, prod = 1;
        for (int j = i; j < n; j++) {
            sum += nums[j];
            prod *= nums[j];
            if (sum == prod) count++;
            if (prod > 1e9) break;
        }
    }
    return count;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

#include <stdlib.h>

int mysticSubarrays(int nums[], int n) {
    int count = 0;
    for (int i = 0; i < n; i++) {
        long long sum = 0, prod = 1;
        for (int j = i; j < n; j++) {
            sum += nums[j];
            prod *= nums[j];
            if (sum == prod) count++;
            if (prod > 1000000000) break;
        }
    }
    return count;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function mysticSubarrays(nums) {
    let n = nums.length, count = 0;
    for (let i = 0; i < n; i++) {
        let sum = 0, prod = 1;
        for (let j = i; j < n; j++) {
            sum += nums[j];
            prod *= nums[j];
            if (sum === prod) count++;
            if (prod > 1e9) break;
        }
    }
    return count;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def mysticSubarrays(nums):
    n = len(nums)
    count = 0
    for i in range(n):
        s = 0
        p = 1
        for j in range(i, n):
            s += nums[j]
            p *= nums[j]
            if s == p:
                count += 1
            if p > 1e9:
                break
    return count

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
