## CPP

### SOLUTION

vector<int> kthSmallestPrimeFraction(vector<int>& arr, int k) {
    int n = arr.size();
    double low = 0.0, high = 1.0;
    int p = 0, q = 1;

    while (true) {
        double mid = (low + high) / 2.0;
        int count = 0;
        p = 0; q = 1;
        int j = 1;

        for (int i = 0; i < n; i++) {
            while (j < n && arr[i] > mid * arr[j]) j++;
            if (j == n) break;
            count += (n - j);
            if ((long long)arr[i] * q > (long long)p * arr[j]) {
                p = arr[i];
                q = arr[j];
            }
        }

        if (count == k) return {p, q};
        if (count < k) low = mid;
        else high = mid;
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVA

### SOLUTION

public static int[] kthSmallestPrimeFraction(int[] arr, int k) {
    int n = arr.length;
    double low = 0.0, high = 1.0;
    int p = 0, q = 1;

    while (true) {
        double mid = (low + high) / 2.0;
        int count = 0;
        p = 0; q = 1;
        int j = 1;

        for (int i = 0; i < n; i++) {
            while (j < n && arr[i] > mid * arr[j]) j++;
            if (j == n) break;
            count += (n - j);
            if ((long)arr[i] * q > (long)p * arr[j]) {
                p = arr[i];
                q = arr[j];
            }
        }

        if (count == k) return new int[]{p, q};
        if (count < k) low = mid;
        else high = mid;
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## C

### SOLUTION

void kthSmallestPrimeFraction(int arr[], int n, int k, int* numerator, int* denominator) {
    double low = 0.0, high = 1.0;
    int p = 0, q = 1;

    while (1) {
        double mid = (low + high) / 2.0;
        int count = 0;
        p = 0; q = 1;
        int j = 1;

        for (int i = 0; i < n; i++) {
            while (j < n && arr[i] > mid * arr[j]) j++;
            if (j == n) break;
            count += (n - j);
            if ((long long)arr[i] * q > (long long)p * arr[j]) {
                p = arr[i];
                q = arr[j];
            }
        }

        if (count == k) {
            *numerator = p;
            *denominator = q;
            return;
        }
        if (count < k) low = mid;
        else high = mid;
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## JAVASCRIPT

### SOLUTION

function kthSmallestPrimeFraction(arr, k) {
    const n = arr.length;
    let low = 0.0, high = 1.0;
    let p = 0, q = 1;

    while (true) {
        const mid = (low + high) / 2;
        let count = 0;
        p = 0; q = 1;
        let j = 1;

        for (let i = 0; i < n; i++) {
            while (j < n && arr[i] > mid * arr[j]) j++;
            if (j === n) break;
            count += (n - j);
            if (arr[i] * q > p * arr[j]) {
                p = arr[i];
                q = arr[j];
            }
        }

        if (count === k) return [p, q];
        if (count < k) low = mid;
        else high = mid;
    }
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512



## PYTHON

### SOLUTION

def kth_smallest_prime_fraction(arr, k):
    n = len(arr)
    low, high = 0.0, 1.0

    while True:
        mid = (low + high) / 2
        count = 0
        p, q = 0, 1
        j = 1

        for i in range(n):
            while j < n and arr[i] > mid * arr[j]:
                j += 1
            if j == n:
                break
            count += (n - j)
            if arr[i] * q > p * arr[j]:
                p, q = arr[i], arr[j]

        if count == k:
            return [p, q]
        if count < k:
            low = mid
        else:
            high = mid

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
