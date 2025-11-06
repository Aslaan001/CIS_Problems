## CPP

### SOLUTION

int bitwiseHarmony(vector<int>& nums) {
    int n = nums.size();
    bool allEqual = true;
    for (int i = 1; i < n; i++) {
        if (nums[i] != nums[0]) {
            allEqual = false;
            break;
        }
    }
    if (allEqual) return 0;
    int totalAnd = nums[0];
    for (int i = 1; i < n; i++) totalAnd &= nums[i];
    return 1;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVA

### SOLUTION

public static int bitwiseHarmony(int[] nums) {
    int n = nums.length;
    boolean allEqual = true;
    for (int i = 1; i < n; i++) {
        if (nums[i] != nums[0]) {
            allEqual = false;
            break;
        }
    }
    if (allEqual) return 0;
    int totalAnd = nums[0];
    for (int i = 1; i < n; i++) totalAnd &= nums[i];
    return 1;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## C

### SOLUTION

int bitwiseHarmony(int* nums, int n) {
    int allEqual = 1;
    for (int i = 1; i < n; i++) {
        if (nums[i] != nums[0]) {
            allEqual = 0;
            break;
        }
    }
    if (allEqual) return 0;
    int totalAnd = nums[0];
    for (int i = 1; i < n; i++) totalAnd &= nums[i];
    return 1;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## JAVASCRIPT

### SOLUTION

function bitwiseHarmony(nums) {
    const n = nums.length;
    let allEqual = true;
    for (let i = 1; i < n; i++) {
        if (nums[i] !== nums[0]) {
            allEqual = false;
            break;
        }
    }
    if (allEqual) return 0;
    let totalAnd = nums[0];
    for (let i = 1; i < n; i++) totalAnd &= nums[i];
    return 1;
}

### METADATA

TimeLimit
1000

MemoryLimit
512


## PYTHON

### SOLUTION

def bitwise_harmony(nums):
    if all(x == nums[0] for x in nums):
        return 0
    total_and = nums[0]
    for x in nums[1:]:
        total_and &= x
    return 1

### METADATA

TimeLimit
1000

MemoryLimit
512
