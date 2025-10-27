## CPP

### SOLUTION

double Median(vector<int>& arr) {
    int n = arr.size();
    sort(arr.begin(), arr.end());
    if (n % 2 == 1)
        return arr[n / 2];
    else
        return (arr[n / 2 - 1] + arr[n / 2]) / 2.0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static double Median(int[] arr) {
    Arrays.sort(arr);
    int n = arr.length;
    if (n % 2 == 1)
        return arr[n / 2];
    else
        return (arr[n / 2 - 1] + arr[n / 2]) / 2.0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

#include <stdio.h>
#include <stdlib.h>

int cmp(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

double Median(int arr[], int n) {
    qsort(arr, n, sizeof(int), cmp);
    if (n % 2 == 1)
        return arr[n / 2];
    else
        return (arr[n / 2 - 1] + arr[n / 2]) / 2.0;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function Median(arr) {
    arr.sort((a, b) => a - b);
    const n = arr.length;
    if (n % 2 === 1) return arr[Math.floor(n / 2)];
    return (arr[n / 2 - 1] + arr[n / 2]) / 2;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def Median(arr):
    arr.sort()
    n = len(arr)
    if n % 2 == 1:
        return arr[n // 2]
    else:
        return (arr[n // 2 - 1] + arr[n // 2]) / 2

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
