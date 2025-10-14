## CPP

### SOLUTION

int averageOfStars(vector<int>& nums) {
    long long sum = 0;
    for (int x : nums) sum += x;
    return sum / nums.size();
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int averageOfStars(int[] nums) {
    long sum = 0;
    for (int x : nums) sum += x;
    return (int)(sum / nums.length);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int averageOfStars(int nums[], int n) {
    long long sum = 0;
    for (int i = 0; i < n; i++) sum += nums[i];
    return sum / n;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function averageOfStars(nums) {
  let sum = 0;
  for (const x of nums) sum += x;
  return Math.floor(sum / nums.length);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def averageOfStars(nums):
    return sum(nums) // len(nums)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
