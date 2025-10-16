## CPP

### SOLUTION

int firstIndependentNumber(vector<int>& nums) {
    int n = nums.size();
    for (int i = 1; i < n; i++) {
        bool divisible = false;
        for (int j = 0; j < i; j++) {
            if (nums[i] % nums[j] == 0) {
                divisible = true;
                break;
            }
        }
        if (!divisible) return i;
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

public static int firstIndependentNumber(int[] nums) {
    int n = nums.length;
    for (int i = 1; i < n; i++) {
        boolean divisible = false;
        for (int j = 0; j < i; j++) {
            if (nums[i] % nums[j] == 0) {
                divisible = true;
                break;
            }
        }
        if (!divisible) return i;
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

int firstIndependentNumber(int nums[], int n) {
    for (int i = 1; i < n; i++) {
        int divisible = 0;
        for (int j = 0; j < i; j++) {
            if (nums[i] % nums[j] == 0) {
                divisible = 1;
                break;
            }
        }
        if (!divisible) return i;
    }
    return -1;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function firstIndependentNumber(nums) {
    const n = nums.length;
    for (let i = 1; i < n; i++) {
        let divisible = false;
        for (let j = 0; j < i; j++) {
            if (nums[i] % nums[j] === 0) {
                divisible = true;
                break;
            }
        }
        if (!divisible) return i;
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

def firstIndependentNumber(nums):
    n = len(nums)
    for i in range(1, n):
        divisible = False
        for j in range(i):
            if nums[i] % nums[j] == 0:
                divisible = True
                break
        if not divisible:
            return i
    return -1

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
