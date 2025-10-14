## CPP

### SOLUTION

vector<int> mergeLoot(vector<int>& nums1, vector<int>& nums2) {
    int n = nums1.size(), m = nums2.size();
    vector<int> result(n + m);
    int i = 0, j = 0, k = 0;
    while (i < n && j < m) {
        if (nums1[i] <= nums2[j]) result[k++] = nums1[i++];
        else result[k++] = nums2[j++];
    }
    while (i < n) result[k++] = nums1[i++];
    while (j < m) result[k++] = nums2[j++];
    return result;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512

## JAVA

### SOLUTION

public static int[] mergeLoot(int[] nums1, int[] nums2) {
    int n = nums1.length, m = nums2.length;
    int[] result = new int[n + m];
    int i = 0, j = 0, k = 0;
    while (i < n && j < m) {
        if (nums1[i] <= nums2[j]) result[k++] = nums1[i++];
        else result[k++] = nums2[j++];
    }
    while (i < n) result[k++] = nums1[i++];
    while (j < m) result[k++] = nums2[j++];
    return result;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512

## C

### SOLUTION

int* mergeLoot(int* nums1, int n, int* nums2, int m, int* size) {
    *size = n + m;
    int* result = (int*)malloc(*size * sizeof(int));
    int i = 0, j = 0, k = 0;
    while (i < n && j < m) {
        if (nums1[i] <= nums2[j]) result[k++] = nums1[i++];
        else result[k++] = nums2[j++];
    }
    while (i < n) result[k++] = nums1[i++];
    while (j < m) result[k++] = nums2[j++];
    return result;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512

## JAVASCRIPT

### SOLUTION

function mergeLoot(nums1, nums2) {
    const result = [];
    let i = 0, j = 0;
    while (i < nums1.length && j < nums2.length) {
        if (nums1[i] <= nums2[j]) result.push(nums1[i++]);
        else result.push(nums2[j++]);
    }
    while (i < nums1.length) result.push(nums1[i++]);
    while (j < nums2.length) result.push(nums2[j++]);
    return result;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512

## PYTHON

### SOLUTION

def mergeLoot(nums1, nums2):
    result = []
    i = j = 0
    while i < len(nums1) and j < len(nums2):
        if nums1[i] <= nums2[j]:
            result.append(nums1[i])
            i += 1
        else:
            result.append(nums2[j])
            j += 1
    while i < len(nums1):
        result.append(nums1[i])
        i += 1
    while j < len(nums2):
        result.append(nums2[j])
        j += 1
    return result

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
