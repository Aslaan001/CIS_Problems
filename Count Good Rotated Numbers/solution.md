## CPP

### SOLUTION

int countGoodRotated(int n) {
    int res = 0;
    for (int i = 1; i <= n; i++) {
        int x = i;
        bool seenGood = false;
        bool ok = true;
        while (x) {
            int d = x % 10;
            if (d == 3 || d == 4 || d == 7) {
                ok = false;
                break;
            }
            if (d == 2 || d == 5 || d == 6 || d == 9) {
                seenGood = true;
            }
            x /= 10;
        }
        if (ok && seenGood) res++;
    }
    return res;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## JAVA

### SOLUTION

public static int countGoodRotated(int n) {
    int res = 0;
    for (int i = 1; i <= n; i++) {
        int x = i;
        boolean seenGood = false;
        boolean ok = true;
        while (x > 0) {
            int d = x % 10;
            if (d == 3 || d == 4 || d == 7) {
                ok = false;
                break;
            }
            if (d == 2 || d == 5 || d == 6 || d == 9) {
                seenGood = true;
            }
            x /= 10;
        }
        if (ok && seenGood) res++;
    }
    return res;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## C

### SOLUTION

int countGoodRotated(int n) {
    int res = 0;
    for (int i = 1; i <= n; i++) {
        int x = i;
        int seenGood = 0;
        int ok = 1;
        while (x > 0) {
            int d = x % 10;
            if (d == 3 || d == 4 || d == 7) {
                ok = 0;
                break;
            }
            if (d == 2 || d == 5 || d == 6 || d == 9) {
                seenGood = 1;
            }
            x /= 10;
        }
        if (ok && seenGood) res++;
    }
    return res;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## JAVASCRIPT

### SOLUTION

function countGoodRotated(n) {
    let res = 0;
    for (let i = 1; i <= n; i++) {
        let x = i;
        let seenGood = false;
        let ok = true;
        while (x > 0) {
            let d = x % 10;
            if (d === 3 || d === 4 || d === 7) {
                ok = false;
                break;
            }
            if (d === 2 || d === 5 || d === 6 || d === 9) {
                seenGood = true;
            }
            x = Math.floor(x / 10);
        }
        if (ok && seenGood) res++;
    }
    return res;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512


## PYTHON

### SOLUTION

def count_good_rotated(n):
    res = 0
    for i in range(1, n + 1):
        x = i
        seen_good = False
        ok = True
        while x > 0:
            d = x % 10
            if d in (3, 4, 7):
                ok = False
                break
            if d in (2, 5, 6, 9):
                seen_good = True
            x //= 10
        if ok and seen_good:
            res += 1
    return res

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
