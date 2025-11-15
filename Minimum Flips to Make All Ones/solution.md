## CPP

### SOLUTION


int minFlips(vector<int>& nums) {
    int flips = 0;
    int state = 0; // 0 = normal, 1 = flipped
    for (int x : nums) {
        int val = x ^ state;
        if (val == 0) {
            flips++;
            state ^= 1;
        }
    }
    return flips;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int minFlips(int[] nums) {
    int flips = 0, state = 0;
    for (int x : nums) {
        int val = x ^ state;
        if (val == 0) {
            flips++;
            state ^= 1;
        }
    }
    return flips;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION


int minFlips(int* nums, int n) {
    int flips = 0, state = 0;
    for (int i = 0; i < n; i++) {
        int val = nums[i] ^ state;
        if (val == 0) {
            flips++;
            state ^= 1;
        }
    }
    return flips;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function minFlips(nums) {
  let flips = 0, state = 0;
  for (let x of nums) {
    let val = x ^ state;
    if (val === 0) {
      flips++;
      state ^= 1;
    }
  }
  return flips;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def min_flips(nums):
    flips = 0
    state = 0
    for x in nums:
        val = x ^ state
        if val == 0:
            flips += 1
            state ^= 1
    return flips

### METADATA

TimeLimit  
1000

MemoryLimit  
512
