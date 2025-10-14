## CPP

### SOLUTION

int maxSubarraySum(vector<int>& nums) {
    int maxEnding = nums[0], maxSoFar = nums[0];
    for (int i = 1; i < nums.size(); i++) {
        maxEnding = max(nums[i], maxEnding + nums[i]);
        maxSoFar = max(maxSoFar, maxEnding);
    }
    return maxSoFar;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

 public static int maxSubarraySum(int[] nums) {
        int maxEnding = nums[0], maxSoFar = nums[0];
        for (int i = 1; i < nums.length; i++) {
            maxEnding = Math.max(nums[i], maxEnding + nums[i]);
            maxSoFar = Math.max(maxSoFar, maxEnding);
        }
        return maxSoFar;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int maxSubarraySum(int nums[], int n) {
    int maxEnding = nums[0], maxSoFar = nums[0];
    for (int i = 1; i < n; i++) {
        maxEnding = nums[i] > maxEnding + nums[i] ? nums[i] : maxEnding + nums[i];
        maxSoFar = maxEnding > maxSoFar ? maxEnding : maxSoFar;
    }
    return maxSoFar;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function maxSubarraySum(nums) {
  let maxEnding = nums[0], maxSoFar = nums[0];
  for (let i = 1; i < nums.length; i++) {
    maxEnding = Math.max(nums[i], maxEnding + nums[i]);
    maxSoFar = Math.max(maxSoFar, maxEnding);
  }
  return maxSoFar;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def maxSubarraySum(nums):
    max_ending = max_so_far = nums[0]
    for x in nums[1:]:
        max_ending = max(x, max_ending + x)
        max_so_far = max(max_so_far, max_ending)
    return max_so_far

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
