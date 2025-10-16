## CPP

### SOLUTION

int firstPeakIndex(vector<int>& arr) {
    long long total = 0;
    for (int val : arr) total += val;
    long long leftSum = 0;
    for (int i = 0; i < arr.size(); i++) {
        long long rightSum = total - leftSum - arr[i];
        if (leftSum < arr[i] && rightSum < arr[i]) return i;
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

public static int firstPeakIndex(int[] arr) {
    long total = 0;
    for (int val : arr) total += val;
    long leftSum = 0;
    for (int i = 0; i < arr.length; i++) {
        long rightSum = total - leftSum - arr[i];
        if (leftSum < arr[i] && rightSum < arr[i]) return i;
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

int firstPeakIndex(int nums[], int n) {
    long long total = 0;
    for (int i = 0; i < n; i++) total += nums[i];
    long long leftSum = 0;
    for (int i = 0; i < n; i++) {
        long long rightSum = total - leftSum - nums[i];
        if (leftSum < nums[i] && rightSum < nums[i]) return i;
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

function firstPeakIndex(nums) {
    let total = nums.reduce((a, b) => a + b, 0);
    let leftSum = 0;
    for (let i = 0; i < nums.length; i++) {
        let rightSum = total - leftSum - nums[i];
        if (leftSum < nums[i] && rightSum < nums[i]) return i;
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

def firstPeakIndex(nums):
    total = sum(nums)
    leftSum = 0
    for i, val in enumerate(nums):
        rightSum = total - leftSum - val
        if leftSum < val and rightSum < val:
            return i
        leftSum += val
    return -1

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
