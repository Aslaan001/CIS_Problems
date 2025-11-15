## CPP

### SOLUTION
int solve(const vector<int>& nums, int k){
    if(k <= 1) return 0;
    long long prod = 1;
    int left = 0, ans = 0;
    for(int right=0; right<nums.size(); right++){
        prod *= nums[right];
        while(prod >= k){
            prod /= nums[left];
            left++;
        }
        ans += right - left + 1;
    }
    return ans;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION
static int solve(int[] nums, int k){
    if(k <= 1) return 0;
    long prod = 1;
    int left = 0, ans = 0;
    for(int right=0; right<nums.length; right++){
        prod *= nums[right];
        while(prod >= k){
            prod /= nums[left];
            left++;
        }
        ans += right - left + 1;
    }
    return ans;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION
int solve(int* arr, int n, int k){
    if(k <= 1) return 0;
    long long prod = 1;
    int left = 0, ans = 0;
    for(int right=0; right<n; right++){
        prod *= arr[right];
        while(prod >= k){
            prod /= arr[left];
            left++;
        }
        ans += right - left + 1;
    }
    return ans;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION
function solve(nums, k){
    if(k <= 1) return 0;
    let prod = 1, left = 0, ans = 0;
    for(let right=0; right<nums.length; right++){
        prod *= nums[right];
        while(prod >= k){
            prod /= nums[left];
            left++;
        }
        ans += right - left + 1;
    }
    return ans;
}

### METADATA
**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION
def solve(arr, k):
    if k <= 1:
        return 0
    prod = 1
    left = 0
    ans = 0
    for right, val in enumerate(arr):
        prod *= val
        while prod >= k:
            prod //= arr[left]
            left += 1
        ans += right - left + 1
    return ans

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128
