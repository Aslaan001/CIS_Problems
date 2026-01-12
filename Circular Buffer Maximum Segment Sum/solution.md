## CPP

### SOLUTION

int maxCircularSegmentSum(vector<int>& nums) {
    int total = 0;
    int curMax = 0, maxSum = nums[0];
    int curMin = 0, minSum = nums[0];

    for (int x : nums) {
        curMax = max(x, curMax + x);
        maxSum = max(maxSum, curMax);

        curMin = min(x, curMin + x);
        minSum = min(minSum, curMin);

        total += x;
    }

    if (maxSum < 0) return maxSum;
    return max(maxSum, total - minSum);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int maxCircularSegmentSum(int[] nums) {
    int total = 0;
    int curMax = 0, maxSum = nums[0];
    int curMin = 0, minSum = nums[0];

    for (int x : nums) {
        curMax = Math.max(x, curMax + x);
        maxSum = Math.max(maxSum, curMax);

        curMin = Math.min(x, curMin + x);
        minSum = Math.min(minSum, curMin);

        total += x;
    }

    if (maxSum < 0) return maxSum;
    return Math.max(maxSum, total - minSum);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

int maxCircularSegmentSum(int nums[], int n) {
    int total = 0;
    int curMax = 0, maxSum = nums[0];
    int curMin = 0, minSum = nums[0];

    for (int i = 0; i < n; i++) {
        int x = nums[i];

        curMax = (x > curMax + x) ? x : curMax + x;
        maxSum = (maxSum > curMax) ? maxSum : curMax;

        curMin = (x < curMin + x) ? x : curMin + x;
        minSum = (minSum < curMin) ? minSum : curMin;

        total += x;
    }

    if (maxSum < 0) return maxSum;
    return (total - minSum > maxSum) ? (total - minSum) : maxSum;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function maxCircularSegmentSum(nums) {
  let total = 0;
  let curMax = 0, maxSum = nums[0];
  let curMin = 0, minSum = nums[0];

  for (const x of nums) {
    curMax = Math.max(x, curMax + x);
    maxSum = Math.max(maxSum, curMax);

    curMin = Math.min(x, curMin + x);
    minSum = Math.min(minSum, curMin);

    total += x;
  }

  if (maxSum < 0) return maxSum;
  return Math.max(maxSum, total - minSum);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def max_circular_segment_sum(nums):
    total = 0
    cur_max = 0
    max_sum = nums[0]
    cur_min = 0
    min_sum = nums[0]

    for x in nums:
        cur_max = max(x, cur_max + x)
        max_sum = max(max_sum, cur_max)

        cur_min = min(x, cur_min + x)
        min_sum = min(min_sum, cur_min)

        total += x

    if max_sum < 0:
        return max_sum
    return max(max_sum, total - min_sum)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
