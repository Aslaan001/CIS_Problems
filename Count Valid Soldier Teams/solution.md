## CPP

### SOLUTION

int countValidTeams(vector<int>& nums) {
    int n = nums.size();
    int ans = 0;
    for (int j = 0; j < n; j++) {
        int leftLess = 0, leftGreater = 0;
        int rightLess = 0, rightGreater = 0;

        for (int i = 0; i < j; i++) {
            if (nums[i] < nums[j]) leftLess++;
            else if (nums[i] > nums[j]) leftGreater++;
        }

        for (int k = j + 1; k < n; k++) {
            if (nums[k] > nums[j]) rightGreater++;
            else if (nums[k] < nums[j]) rightLess++;
        }

        ans += leftLess * rightGreater;
        ans += leftGreater * rightLess;
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

public static int countValidTeams(int[] nums) {
    int n = nums.length;
    int ans = 0;

    for (int j = 0; j < n; j++) {
        int leftLess = 0, leftGreater = 0;
        int rightLess = 0, rightGreater = 0;

        for (int i = 0; i < j; i++) {
            if (nums[i] < nums[j]) leftLess++;
            else if (nums[i] > nums[j]) leftGreater++;
        }

        for (int k = j + 1; k < n; k++) {
            if (nums[k] > nums[j]) rightGreater++;
            else if (nums[k] < nums[j]) rightLess++;
        }

        ans += leftLess * rightGreater;
        ans += leftGreater * rightLess;
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

int countValidTeams(int* nums, int n) {
    int ans = 0;

    for (int j = 0; j < n; j++) {
        int leftLess = 0, leftGreater = 0;
        int rightLess = 0, rightGreater = 0;

        for (int i = 0; i < j; i++) {
            if (nums[i] < nums[j]) leftLess++;
            else if (nums[i] > nums[j]) leftGreater++;
        }

        for (int k = j + 1; k < n; k++) {
            if (nums[k] > nums[j]) rightGreater++;
            else if (nums[k] < nums[j]) rightLess++;
        }

        ans += leftLess * rightGreater;
        ans += leftGreater * rightLess;
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

function countValidTeams(nums) {
  let n = nums.length;
  let ans = 0;

  for (let j = 0; j < n; j++) {
    let leftLess = 0, leftGreater = 0;
    let rightLess = 0, rightGreater = 0;

    for (let i = 0; i < j; i++) {
      if (nums[i] < nums[j]) leftLess++;
      else if (nums[i] > nums[j]) leftGreater++;
    }

    for (let k = j + 1; k < n; k++) {
      if (nums[k] > nums[j]) rightGreater++;
      else if (nums[k] < nums[j]) rightLess++;
    }

    ans += leftLess * rightGreater;
    ans += leftGreater * rightLess;
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

def count_valid_teams(nums):
    n = len(nums)
    ans = 0

    for j in range(n):
        leftLess = leftGreater = 0
        rightLess = rightGreater = 0

        for i in range(j):
            if nums[i] < nums[j]:
                leftLess += 1
            elif nums[i] > nums[j]:
                leftGreater += 1

        for k in range(j + 1, n):
            if nums[k] > nums[j]:
                rightGreater += 1
            elif nums[k] < nums[j]:
                rightLess += 1

        ans += leftLess * rightGreater
        ans += leftGreater * rightLess

    return ans

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512
