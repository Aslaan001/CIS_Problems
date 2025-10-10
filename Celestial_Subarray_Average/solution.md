## CPP

### SOLUTION

double ancientScroll(vector<int>& nums, int k) {
    double windowSum = 0;
    for (int i = 0; i < k; i++) windowSum += nums[i];
    double maxSum = windowSum;
    for (int i = k; i < nums.size(); i++) {
        windowSum += nums[i] - nums[i - k];
        maxSum = max(maxSum, windowSum);
    }
    return maxSum / k;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static double ancientScroll(int[] nums, int k) {
    double windowSum = 0;
    for (int i = 0; i < k; i++) windowSum += nums[i];
    double maxSum = windowSum;
    for (int i = k; i < nums.length; i++) {
        windowSum += nums[i] - nums[i - k];
        maxSum = Math.max(maxSum, windowSum);
    }
    return maxSum / k;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

double ancientScroll(int n, int nums[], int k) {
    double windowSum = 0;
    for (int i = 0; i < k; i++) windowSum += nums[i];
    double maxSum = windowSum;
    for (int i = k; i < n; i++) {
        windowSum += nums[i] - nums[i - k];
        if (windowSum > maxSum) maxSum = windowSum;
    }
    return maxSum / k;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function ancientScroll(nums, k) {
  let windowSum = 0;
  for (let i = 0; i < k; i++) windowSum += nums[i];
  let maxSum = windowSum;
  for (let i = k; i < nums.length; i++) {
    windowSum += nums[i] - nums[i - k];
    maxSum = Math.max(maxSum, windowSum);
  }
  return maxSum / k;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def ancientScroll(nums, k):
    window_sum = sum(nums[:k])
    max_sum = window_sum
    for i in range(k, len(nums)):
        window_sum += nums[i] - nums[i - k]
        max_sum = max(max_sum, window_sum)
    return max_sum / k

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
