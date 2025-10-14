## CPP

### SOLUTION

long long sumProductDifference(vector<int>& nums) {
    long long sum = 0, prod = 1;
    for (int x : nums) {
        sum += x;
        prod *= x;
    }
    return prod - sum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static long sumProductDifference(int[] nums) {
    long sum = 0, prod = 1;
    for (int x : nums) {
        sum += x;
        prod *= x;
    }
    return (int)(prod - sum);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

long long sumProductDifference(int nums[], int n) {
    long long sum = 0, prod = 1;
    for (int i = 0; i < n; i++) {
        sum += nums[i];
        prod *= nums[i];
    }
    return (int)(prod - sum);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function sumProductDifference(nums) {
  let sum = 0, prod = 1;
  for (const x of nums) {
    sum += x;
    prod *= x;
  }
  return prod - sum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def sumProductDifference(nums):
    sum_ = sum(nums)
    prod = 1
    for x in nums:
        prod *= x
    return prod - sum_

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
