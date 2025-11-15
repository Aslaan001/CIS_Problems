## CPP

### SOLUTION

int solve(const vector<int>& nums) {
    int total = accumulate(nums.begin(), nums.end(), 0);
    int left = 0;
    for(int i = 0; i < nums.size(); i++){
        if(left == total - left - nums[i]) return i;
        left += nums[i];
    }
    return -1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION

static int solve(int[] nums){
        int total = 0;
        for(int x : nums) total += x;
        int left = 0;
        for(int i = 0; i < nums.length; i++){
            if(left == total - left - nums[i]) return i;
            left += nums[i];
        }
        return -1;
    }

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION

int solve(int* arr, int n){
    int total = 0;
    for(int i = 0; i < n; i++) total += arr[i];

    int left = 0;
    for(int i = 0; i < n; i++){
        if(left == total - left - arr[i]) return i;
        left += arr[i];
    }
    return -1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION

function solve(nums){
    let total=nums.reduce((a,b)=>a+b,0);
    let left=0;
    for(let i=0;i<nums.length;i++){
        if(left === total-left-nums[i]) return i;
        left+=nums[i];
    }
    return -1;
}

### METADATA

**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION

def solve(arr):
    total=sum(arr)
    left=0
    for i,v in enumerate(arr):
        if left == total-left-v:
            return i
        left+=v
    return -1

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128
