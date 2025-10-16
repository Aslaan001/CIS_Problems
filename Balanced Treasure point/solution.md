## CPP

### SOLUTION

int balancedTreasurePoint(vector<int>& arr) {
    long long total = 0;
    for (int val : arr) total += val;
    long long leftSum = 0;
    for (int i = 0; i < arr.size(); i++) {
        if (leftSum == total - leftSum - arr[i]) return i;
        leftSum += arr[i];
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

public static int balancedTreasurePoint(int[] arr) {
    long total = 0;
    for (int val : arr) total += val;
    long leftSum = 0;
    for (int i = 0; i < arr.length; i++) {
        if (leftSum == total - leftSum - arr[i]) return i;
        leftSum += arr[i];
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

int balancedTreasurePoint(int nums[], int n) {
    long long total = 0;
    for (int i = 0; i < n; i++) total += nums[i];
    long long leftSum = 0;
    for (int i = 0; i < n; i++) {
        if (leftSum == total - leftSum - nums[i]) return i;
        leftSum += nums[i];
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

function balancedTreasurePoint(nums) {
    let total = nums.reduce((a, b) => a + b, 0);
    let leftSum = 0;
    for (let i = 0; i < nums.length; i++) {
        if (leftSum === total - leftSum - nums[i]) return i;
        leftSum += nums[i];
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

def balancedTreasurePoint(nums):
    total = sum(nums)
    leftSum = 0
    for i, val in enumerate(nums):
        if leftSum == total - leftSum - val:
            return i
        leftSum += val
    return -1

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
