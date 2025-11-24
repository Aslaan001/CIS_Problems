## CPP

### SOLUTION

int maxWater(vector<int>& nums) {
    int l = 0, r = nums.size() - 1;
    int ans = 0;
    while (l < r) {
        int h = min(nums[l], nums[r]);
        ans = max(ans, h * (r - l));
        if (nums[l] < nums[r]) l++;
        else r--;
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int maxWater(int[] nums) {
    int l = 0, r = nums.length - 1;
    int ans = 0;
    while (l < r) {
        int h = Math.min(nums[l], nums[r]);
        ans = Math.max(ans, h * (r - l));
        if (nums[l] < nums[r]) l++;
        else r--;
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int maxWater(int nums[], int n) {
    int l = 0, r = n - 1;
    int ans = 0;
    while (l < r) {
        int h = nums[l] < nums[r] ? nums[l] : nums[r];
        int area = h * (r - l);
        if (area > ans) ans = area;
        if (nums[l] < nums[r]) l++;
        else r--;
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function maxWater(nums) {
  let l = 0, r = nums.length - 1;
  let ans = 0;
  while (l < r) {
    const h = Math.min(nums[l], nums[r]);
    ans = Math.max(ans, h * (r - l));
    if (nums[l] < nums[r]) l++;
    else r--;
  }
  return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def maxWater(nums):
    l, r = 0, len(nums) - 1
    ans = 0
    while l < r:
        h = min(nums[l], nums[r])
        ans = max(ans, h * (r - l))
        if nums[l] < nums[r]:
            l += 1
        else:
            r -= 1
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
