## CPP

### SOLUTION

int pow10[] = {1,10,100,1000,10000,100000,1000000,10000000,100000000,1000000000};

long long reverseNumber(long long num){
    long long res = 0;
    while(num > 0){
        res = res * 10 + num % 10;
        num /= 10;
    }
    return res;
}

bool isPrime(long long num){
    if(num < 2) return false;
    for(long long i = 2; i * i <= num; i++){
        if(num % i == 0) return false;
    }
    return true;
}

long long nextPrimeMirror(long long n){
    if(n <= 11){
        if(n <= 2) return 2;
        if(n <= 3) return 3;
        if(n <= 5) return 5;
        if(n <= 7) return 7;
        return 11;
    }

    int d = 0, tmp = n;
    while(tmp > 0){
        d++;
        tmp /= 10;
    }

    for(int len = d; ; len++){
        if(len % 2 == 0) continue;

        int half = len / 2;
        int start = pow10[half - 1];
        int end   = pow10[half];

        for(int left = start; left < end; left++){
            long long rev = reverseNumber(left);

            for(int mid = 0; mid <= 9; mid++){
                long long num = (1LL * left * 10 + mid) * end + rev;
                if(num >= n && isPrime(num)) return num;
            }
        }
    }
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512



## JAVA

### SOLUTION

public static long nextPrimeMirror(long n) {

    if(n <= 11){
        if(n <= 2) return 2;
        if(n <= 3) return 3;
        if(n <= 5) return 5;
        if(n <= 7) return 7;
        return 11;
    }

    int digits = Long.toString(n).length();

    while(true){
        if(digits % 2 == 0){
            digits++;
            continue;
        }

        int half = digits / 2;
        long start = (long)Math.pow(10, half - 1);
        long end   = (long)Math.pow(10, half);

        for(long left = start; left < end; left++){
            long rev = reverse(left);
            for(int mid = 0; mid <= 9; mid++){
                long num = (left * 10 + mid) * end + rev;
                if(num >= n && isPrime(num)) return num;
            }
        }

        digits++;
    }
}

private static long reverse(long x){
    long r = 0;
    while(x > 0){
        r = r * 10 + x % 10;
        x /= 10;
    }
    return r;
}

private static boolean isPrime(long num){
    if(num < 2) return false;
    for(long i = 2; i * i <= num; i++){
        if(num % i == 0) return false;
    }
    return true;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512



## C

### SOLUTION

long long reverseNumber(long long x){
    long long r = 0;
    while(x > 0){
        r = r * 10 + x % 10;
        x /= 10;
    }
    return r;
}

int isPrime(long long x){
    if(x < 2) return 0;
    for(long long i = 2; i * i <= x; i++){
        if(x % i == 0) return 0;
    }
    return 1;
}

long long nextPrimeMirror(long long n){
    if(n <= 11){
        if(n <= 2) return 2;
        if(n <= 3) return 3;
        if(n <= 5) return 5;
        if(n <= 7) return 7;
        return 11;
    }

    int digits = 0;
    long long t = n;
    while(t > 0){
        digits++;
        t /= 10;
    }

    while(1){
        if(digits % 2 == 0){
            digits++;
            continue;
        }

        int half = digits / 2;
        long long start = 1;
        for(int i = 1; i < half; i++) start *= 10;
        long long end = start * 10;

        for(long long left = start; left < end; left++){
            long long rev = reverseNumber(left);

            for(int mid = 0; mid <= 9; mid++){
                long long num = (left * 10 + mid) * end + rev;
                if(num >= n && isPrime(num)) return num;
            }
        }

        digits++;
    }
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512



## JAVASCRIPT

### SOLUTION

function reverseNumber(x){
    let r = 0n;
    while(x > 0n){
        r = r * 10n + (x % 10n);
        x /= 10n;
    }
    return r;
}

function isPrime(x){
    if(x < 2n) return false;
    for(let i = 2n; i * i <= x; i++){
        if(x % i === 0n) return false;
    }
    return true;
}

function nextPrimeMirror(n){
    n = BigInt(n);

    if(n <= 11n){
        if(n <= 2n) return 2n;
        if(n <= 3n) return 3n;
        if(n <= 5n) return 5n;
        if(n <= 7n) return 7n;
        return 11n;
    }

    let digits = n.toString().length;

    while(true){
        if(digits % 2 === 0){
            digits++;
            continue;
        }

        let half = Math.floor(digits / 2);
        let start = 10n ** BigInt(half - 1);
        let end   = 10n ** BigInt(half);

        for(let left = start; left < end; left++){
            let rev = reverseNumber(left);

            for(let mid = 0n; mid <= 9n; mid++){
                let num = (left * 10n + mid) * end + rev;
                if(num >= n && isPrime(num)) return num;
            }
        }

        digits++;
    }
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512



## PYTHON

### SOLUTION

def reverse_num(x):
    r = 0
    while x > 0:
        r = r * 10 + x % 10
        x //= 10
    return r

def is_prime(x):
    if x < 2:
        return False
    i = 2
    while i * i <= x:
        if x % i == 0:
            return False
        i += 1
    return True

def next_prime_mirror(n):

    if n <= 11:
        if n <= 2: return 2
        if n <= 3: return 3
        if n <= 5: return 5
        if n <= 7: return 7
        return 11

    digits = len(str(n))

    while True:
        if digits % 2 == 0:
            digits += 1
            continue

        half = digits // 2
        start = 10 ** (half - 1)
        end   = 10 ** half

        for left in range(start, end):
            rev = reverse_num(left)
            for mid in range(10):
                num = (left * 10 + mid) * end + rev
                if num >= n and is_prime(num):
                    return num

        digits += 1

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
