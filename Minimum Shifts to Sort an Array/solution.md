## CPP

### SOLUTION

long long insertionSortShifts(vector<int>& arr) {
    long long shifts = 0;
    int n = arr.size();
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
            shifts++;
        }
        arr[j + 1] = key;
    }
    return shifts;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

---

## JAVA

### SOLUTION

public static long insertionSortShifts(int[] arr) {
    long shifts = 0;
    int n = arr.length;
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
            shifts++;
        }
        arr[j + 1] = key;
    }
    return shifts;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

---

## C

### SOLUTION

long long insertionSortShifts(int arr[], int n) {
    long long shifts = 0;
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
            shifts++;
        }
        arr[j + 1] = key;
    }
    return shifts;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

---

## JAVASCRIPT

### SOLUTION

function insertionSortShifts(arr) {
    let shifts = 0;
    const n = arr.length;
    for (let i = 1; i < n; i++) {
        let key = arr[i];
        let j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
            shifts++;
        }
        arr[j + 1] = key;
    }
    return shifts;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

---

## PYTHON

### SOLUTION

def insertionSortShifts(arr):
    shifts = 0
    n = len(arr)
    for i in range(1, n):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
            shifts += 1
        arr[j + 1] = key
    return shifts

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
