## CPP

### SOLUTION

long long minBoulders(const vector<long long>& a, int n, long long k) {

    priority_queue<long long> d;
    long long p = 0, s = 0;

    for (int i = 0; i < n; i++) {

        long long x = a[i] % k;

        if (x > p) {
            d.push(p - x);
            s -= d.top();
            d.pop();
        }
        else {
            d.push(p - k - x);
        }

        p = x;
    }

    return s;
}

### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256




## JAVA

### SOLUTION

public static long minBoulders(long[] a, int n, long k) {

    PriorityQueue<Long> d = new PriorityQueue<>(Collections.reverseOrder());
    long p = 0, s = 0;

    for (int i = 0; i < n; i++) {

        long x = a[i] % k;

        if (x > p) {
            d.add(p - x);
            s -= d.poll();
        }
        else {
            d.add(p - k - x);
        }

        p = x;
    }

    return s;
}

### METADATA

**TimeLimit**  
2000

**MemoryLimit**  
256
