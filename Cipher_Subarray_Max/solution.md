## CPP

### SOLUTION

int maxSubarraySum(vector<int>& nums, int k) {
    int n = nums.size();
    int sum = 0;
    for (int i = 0; i < k; i++) sum += nums[i];
    int maxSum = sum;
    for (int i = k; i < n; i++) {
        sum += nums[i] - nums[i - k];
        maxSum = max(maxSum, sum);
    }
    return maxSum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512


## JAVA

### SOLUTION

public static int maxSubarraySum(int[] nums, int k) {
    int n = nums.length;
    int sum = 0;
    for (int i = 0; i < k; i++) sum += nums[i];
    int maxSum = sum;
    for (int i = k; i < n; i++) {
        sum += nums[i] - nums[i - k];
        maxSum = Math.max(maxSum, sum);
    }
    return maxSum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int maxSubarraySum(int n, int nums[], int k) {
    int sum = 0;
    for (int i = 0; i < k; i++) sum += nums[i];
    int maxSum = sum;
    for (int i = k; i < n; i++) {
        sum += nums[i] - nums[i - k];
        if (sum > maxSum) maxSum = sum;
    }
    return maxSum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function maxSubarraySum(nums, k) {
  let sum = 0;
  for (let i = 0; i < k; i++) sum += nums[i];
  let maxSum = sum;
  for (let i = k; i < nums.length; i++) {
    sum += nums[i] - nums[i - k];
    maxSum = Math.max(maxSum, sum);
  }
  return maxSum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def maxSubarraySum(nums, k):
    sum_ = sum(nums[:k])
    max_sum = sum_
    for i in range(k, len(nums)):
        sum_ += nums[i] - nums[i - k]
        max_sum = max(max_sum, sum_)
    return max_sum

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
