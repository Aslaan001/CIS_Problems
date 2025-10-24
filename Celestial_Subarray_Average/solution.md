## CPP

### SOLUTION

double celestialSubarrayAverage(vector<int>& brightness, int k) {
    double windowSum = 0;
    for (int i = 0; i < k; i++) windowSum += brightness[i];
    double maxSum = windowSum;
    for (int i = k; i < brightness.size(); i++) {
        windowSum += brightness[i] - brightness[i - k];
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

public static double celestialSubarrayAverage(int[] brightness, int k) {
    double windowSum = 0;
    for (int i = 0; i < k; i++) windowSum += brightness[i];
    double maxSum = windowSum;
    for (int i = k; i < brightness.length; i++) {
        windowSum += brightness[i] - brightness[i - k];
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

double celestialSubarrayAverage(int n, int brightness[], int k) {
    double windowSum = 0;
    for (int i = 0; i < k; i++) windowSum += brightness[i];
    double maxSum = windowSum;
    for (int i = k; i < n; i++) {
        windowSum += brightness[i] - brightness[i - k];
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

function celestialSubarrayAverage(brightness, k) {
  let windowSum = 0;
  for (let i = 0; i < k; i++) windowSum += brightness[i];
  let maxSum = windowSum;
  for (let i = k; i < brightness.length; i++) {
    windowSum += brightness[i] - brightness[i - k];
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

def celestialSubarrayAverage(brightness, k):
    window_sum = sum(brightness[:k])
    max_sum = window_sum
    for i in range(k, len(brightness)):
        window_sum += brightness[i] - brightness[i - k]
        max_sum = max(max_sum, window_sum)
    return max_sum / k

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
