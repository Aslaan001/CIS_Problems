## CPP

### SOLUTION

long long minimumMovesToOrder(vector<int>& arr) {
    function<long long(int,int)> mergeSort = [&](int l, int r) -> long long {
        if (l >= r) return 0;
        int m = (l + r) / 2;
        long long inv = mergeSort(l, m) + mergeSort(m + 1, r);
        vector<int> temp;
        int i = l, j = m + 1;
        while (i <= m && j <= r) {
            if (arr[i] <= arr[j]) temp.push_back(arr[i++]);
            else {
                temp.push_back(arr[j++]);
                inv += (m - i + 1);
            }
        }
        while (i <= m) temp.push_back(arr[i++]);
        while (j <= r) temp.push_back(arr[j++]);
        for (int k = l; k <= r; k++) arr[k] = temp[k - l];
        return inv;
    };
    return mergeSort(0, arr.size() - 1);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVA

### SOLUTION

public static long minimumMovesToOrder(int[] arr) {
    return mergeSort(arr, 0, arr.length - 1);
}

private static long mergeSort(int[] arr, int l, int r) {
    if (l >= r) return 0;
    int m = (l + r) / 2;
    long inv = mergeSort(arr, l, m) + mergeSort(arr, m + 1, r);
    int[] temp = new int[r - l + 1];
    int i = l, j = m + 1, k = 0;
    while (i <= m && j <= r) {
        if (arr[i] <= arr[j]) temp[k++] = arr[i++];
        else {
            temp[k++] = arr[j++];
            inv += (m - i + 1);
        }
    }
    while (i <= m) temp[k++] = arr[i++];
    while (j <= r) temp[k++] = arr[j++];
    System.arraycopy(temp, 0, arr, l, temp.length);
    return inv;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## C

### SOLUTION

long long mergeSort(int arr[], int l, int r) {
    if (l >= r) return 0;
    int m = (l + r) / 2;
    long long inv = mergeSort(arr, l, m) + mergeSort(arr, m + 1, r);
    int n1 = m - l + 1, n2 = r - m;
    int* left = (int*)malloc(n1 * sizeof(int));
    int* right = (int*)malloc(n2 * sizeof(int));
    for (int i = 0; i < n1; i++) left[i] = arr[l + i];
    for (int i = 0; i < n2; i++) right[i] = arr[m + 1 + i];
    int i = 0, j = 0, k = l;
    while (i < n1 && j < n2) {
        if (left[i] <= right[j]) arr[k++] = left[i++];
        else {
            arr[k++] = right[j++];
            inv += (n1 - i);
        }
    }
    while (i < n1) arr[k++] = left[i++];
    while (j < n2) arr[k++] = right[j++];
    free(left);
    free(right);
    return inv;
}

long long minimumMovesToOrder(int arr[], int n) {
    return mergeSort(arr, 0, n - 1);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## JAVASCRIPT

### SOLUTION

function minimumMovesToOrder(arr) {
    function mergeSort(l, r) {
        if (l >= r) return 0;
        const m = Math.floor((l + r) / 2);
        let inv = mergeSort(l, m) + mergeSort(m + 1, r);
        const temp = [];
        let i = l, j = m + 1;
        while (i <= m && j <= r) {
            if (arr[i] <= arr[j]) temp.push(arr[i++]);
            else {
                temp.push(arr[j++]);
                inv += (m - i + 1);
            }
        }
        while (i <= m) temp.push(arr[i++]);
        while (j <= r) temp.push(arr[j++]);
        for (let k = l; k <= r; k++) arr[k] = temp[k - l];
        return inv;
    }
    return mergeSort(0, arr.length - 1);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  


## PYTHON

### SOLUTION

def minimumMovesToOrder(arr):
    def merge_sort(l, r):
        if l >= r:
            return 0
        m = (l + r) // 2
        inv = merge_sort(l, m) + merge_sort(m + 1, r)
        temp = []
        i, j = l, m + 1
        while i <= m and j <= r:
            if arr[i] <= arr[j]:
                temp.append(arr[i])
                i += 1
            else:
                temp.append(arr[j])
                j += 1
                inv += (m - i + 1)
        while i <= m:
            temp.append(arr[i])
            i += 1
        while j <= r:
            temp.append(arr[j])
            j += 1
        arr[l:r+1] = temp
        return inv
    return merge_sort(0, len(arr) - 1)

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512
