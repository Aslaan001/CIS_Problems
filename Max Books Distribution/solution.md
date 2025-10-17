## CPP

### SOLUTION

bool canDistribute(vector<int>& books, int m, long long k) {
    long long cnt = 0;
    for (auto x : books) cnt += x / k;
    return cnt >= m;
}

int maxBooksDistribution(vector<int>& books, int m) {
    long long l = 1, h = 0, ans = 0;
    for (auto x : books) h += x; // maximum total books
    while (l <= h) {
        long long mid = (l + h) / 2;
        if (canDistribute(books, m, mid)) { ans = mid; l = mid + 1; }
        else h = mid - 1;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVA

### SOLUTION

public static boolean canDistribute(int[] books, int m, long k) {
    long cnt = 0;
    for (int x : books) cnt += x / k;
    return cnt >= m;
}

public static int maxBooksDistribution(int[] books, int m) {
    long l = 1, h = 0, ans = 0;
    for (int x : books) h += x;
    while (l <= h) {
        long mid = (l + h) / 2;
        if (canDistribute(books, m, mid)) { ans = mid; l = mid + 1; }
        else h = mid - 1;
    }
    return (int)ans;
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

bool canDistribute(int books[], int n, int m, long long k) {
    long long cnt = 0;
    for (int i = 0; i < n; i++) cnt += books[i] / k;
    return cnt >= m;
}

int maxBooksDistribution(int books[], int n, int m) {
    long long l = 1, h = 0, ans = 0;
    for (int i = 0; i < n; i++) h += books[i];
    while (l <= h) {
        long long mid = (l + h) / 2;
        if (canDistribute(books, n, m, mid)) { ans = mid; l = mid + 1; }
        else h = mid - 1;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVASCRIPT

### SOLUTION

function canDistribute(books, m, k) {
    let cnt = 0;
    for (const x of books) cnt += Math.floor(x / k);
    return cnt >= m;
}

function maxBooksDistribution(books, m) {
    let l = 1, h = books.reduce((a,b)=>a+b, 0), ans = 0;
    while (l <= h) {
        let mid = Math.floor((l + h)/2);
        if (canDistribute(books, m, mid)) { ans = mid; l = mid + 1; }
        else h = mid - 1;
    }
    return ans;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## PYTHON

### SOLUTION

def canDistribute(books, m, k):
    cnt = 0
    for x in books:
        cnt += x // k
    return cnt >= m

def maxBooksDistribution(books, m):
    l, h, ans = 1, sum(books), 0
    while l <= h:
        mid = (l + h) // 2
        if canDistribute(books, m, mid):
            ans = mid
            l = mid + 1
        else:
            h = mid - 1
    return ans

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
