## CPP

### SOLUTION

string isArraySorted(vector<int>& arr) {
    int n = arr.size();
    for (int i = 1; i < n; i++) {
        if (arr[i] < arr[i - 1])
            return "NO";
    }
    return "YES";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static String isArraySorted(int[] arr) {
    for (int i = 1; i < arr.length; i++) {
        if (arr[i] < arr[i - 1])
            return "NO";
    }
    return "YES";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

#include <stdbool.h>
#include <string.h>

const bool isArraySorted(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        if (arr[i] < arr[i - 1])
            return 0;
    }
    return 1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function isArraySorted(arr) {
    for (let i = 1; i < arr.length; i++) {
        if (arr[i] < arr[i - 1]) return "NO";
    }
    return "YES";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def isArraySorted(arr):
    for i in range(1, len(arr)):
        if arr[i] < arr[i - 1]:
            return "NO"
    return "YES"

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
