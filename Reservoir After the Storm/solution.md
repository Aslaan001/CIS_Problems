## CPP

### SOLUTION

int trappedWater(vector<int>& nums) {
    int n = nums.size();
    int l = 0, r = n - 1;
    int leftMax = 0, rightMax = 0, ans = 0;

    while (l < r) {
        if (nums[l] < nums[r]) {
            if (nums[l] >= leftMax) leftMax = nums[l];
            else ans += leftMax - nums[l];
            l++;
        } else {
            if (nums[r] >= rightMax) rightMax = nums[r];
            else ans += rightMax - nums[r];
            r--;
        }
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

public static int trappedWater(int[] nums) {
    int n = nums.length;
    int l = 0, r = n - 1;
    int leftMax = 0, rightMax = 0, ans = 0;

    while (l < r) {
        if (nums[l] < nums[r]) {
            if (nums[l] >= leftMax) leftMax = nums[l];
            else ans += leftMax - nums[l];
            l++;
        } else {
            if (nums[r] >= rightMax) rightMax = nums[r];
            else ans += rightMax - nums[r];
            r--;
        }
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

int trappedWater(int nums[], int n) {
    int l = 0, r = n - 1;
    int leftMax = 0, rightMax = 0;
    int ans = 0;

    while (l < r) {
        if (nums[l] < nums[r]) {
            if (nums[l] >= leftMax) leftMax = nums[l];
            else ans += leftMax - nums[l];
            l++;
        } else {
            if (nums[r] >= rightMax) rightMax = nums[r];
            else ans += rightMax - nums[r];
            r--;
        }
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

function trappedWater(nums) {
  let l = 0, r = nums.length - 1;
  let leftMax = 0, rightMax = 0, ans = 0;

  while (l < r) {
    if (nums[l] < nums[r]) {
      if (nums[l] >= leftMax) leftMax = nums[l];
      else ans += leftMax - nums[l];
      l++;
    } else {
      if (nums[r] >= rightMax) rightMax = nums[r];
      else ans += rightMax - nums[r];
      r--;
    }
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

def trappedWater(nums):
    l, r = 0, len(nums) - 1
    leftMax = rightMax = 0
    ans = 0

    while l < r:
        if nums[l] < nums[r]:
            if nums[l] >= leftMax:
                leftMax = nums[l]
            else:
                ans += leftMax - nums[l]
            l += 1
        else:
            if nums[r] >= rightMax:
                rightMax = nums[r]
            else:
                ans += rightMax - nums[r]
            r -= 1

    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
