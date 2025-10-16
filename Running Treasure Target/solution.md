## CPP

### SOLUTION

int runningTreasureTarget(vector<int>& arr, int target) {
    long long sum = 0;
    for (int i = 0; i < arr.size(); i++) {
        sum += arr[i];
        if (sum >= target)
            return i;
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

public static int runningTreasureTarget(int[] arr, int target) {
    long sum = 0;
    for (int i = 0; i < arr.length; i++) {
        sum += arr[i];
        if (sum >= target)
            return i;
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

int runningTreasureTarget(int nums[], int n, long long target) {
    long long sum = 0;
    for (int i = 0; i < n; i++) {
        sum += nums[i];
        if (sum >= target)
            return i;
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

function runningTreasureTarget(nums, target) {
  let sum = 0;
  for (let i = 0; i < nums.length; i++) {
    sum += nums[i];
    if (sum >= target) return i;
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

def runningTreasureTarget(nums, target):
    total = 0
    for i, val in enumerate(nums):
        total += val
        if total >= target:
            return i
    return -1

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
