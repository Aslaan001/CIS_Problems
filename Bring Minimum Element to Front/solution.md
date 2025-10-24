## CPP

### SOLUTION

void bringMinToFront(vector<int>& nums) {
    int n = nums.size();
    int minIndex = 0;
    for (int i = 1; i < n; i++) {
        if (nums[i] < nums[minIndex]) {
            minIndex = i;
        }
    }
    swap(nums[0], nums[minIndex]);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static void bringMinToFront(int[] nums) {
    int n = nums.length;
    int minIndex = 0;
    for (int i = 1; i < n; i++) {
        if (nums[i] < nums[minIndex]) {
            minIndex = i;
        }
    }
    int temp = nums[0];
    nums[0] = nums[minIndex];
    nums[minIndex] = temp;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

void bringMinToFront(int nums[], int n) {
    int minIndex = 0;
    for (int i = 1; i < n; i++) {
        if (nums[i] < nums[minIndex]) {
            minIndex = i;
        }
    }
    int temp = nums[0];
    nums[0] = nums[minIndex];
    nums[minIndex] = temp;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function bringMinToFront(nums) {
    let minIndex = 0;
    for (let i = 1; i < nums.length; i++) {
        if (nums[i] < nums[minIndex]) minIndex = i;
    }
    [nums[0], nums[minIndex]] = [nums[minIndex], nums[0]];
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def bring_min_to_front(nums):
    min_index = 0
    for i in range(1, len(nums)):
        if nums[i] < nums[min_index]:
            min_index = i
    nums[0], nums[min_index] = nums[min_index], nums[0]

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
