## CPP

### SOLUTION

string tripletSumExists(vector<int>& arr, int k) {
    int n = arr.size();
    sort(arr.begin(), arr.end());
    for (int i = 0; i < n - 2; i++) {
        int left = i + 1, right = n - 1;
        while (left < right) {
            int sum = arr[i] + arr[left] + arr[right];
            if (sum == k)
                return "YES";
            else if (sum < k)
                left++;
            else
                right--;
        }
    }
    return "NO";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static String tripletSumExists(int[] arr, int k) {
    Arrays.sort(arr);
    int n = arr.length;
    for (int i = 0; i < n - 2; i++) {
        int left = i + 1, right = n - 1;
        while (left < right) {
            int sum = arr[i] + arr[left] + arr[right];
            if (sum == k)
                return "YES";
            else if (sum < k)
                left++;
            else
                right--;
        }
    }
    return "NO";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

#include <stdbool.h>
#include <stdlib.h>

int cmpfunc(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

const bool tripletSumExists(int arr[], int n, int k) {
    qsort(arr, n, sizeof(int), cmpfunc);
    for (int i = 0; i < n - 2; i++) {
        int left = i + 1, right = n - 1;
        while (left < right) {
            int sum = arr[i] + arr[left] + arr[right];
            if (sum == k)
                return 1;
            else if (sum < k)
                left++;
            else
                right--;
        }
    }
    return 0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function tripletSumExists(arr, k) {
    arr.sort((a, b) => a - b);
    for (let i = 0; i < arr.length - 2; i++) {
        let left = i + 1,
            right = arr.length - 1;
        while (left < right) {
            const sum = arr[i] + arr[left] + arr[right];
            if (sum === k)
                return "YES";
            else if (sum < k)
                left++;
            else
                right--;
        }
    }
    return "NO";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def tripletSumExists(arr, k):
    arr.sort()
    n = len(arr)
    for i in range(n - 2):
        left, right = i + 1, n - 1
        while left < right:
            s = arr[i] + arr[left] + arr[right]
            if s == k:
                return "YES"
            elif s < k:
                left += 1
            else:
                right -= 1
    return "NO"

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
