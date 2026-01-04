## CPP

### SOLUTION

int dp[1001];
int mod = 1000000007;

int solve(int day, int delay, int forget, int n) {
    if (day + delay > n) return 1;
    if (dp[day] != -1) return dp[day];

    long long ans = 1;

    for (int i = day + delay; i <= min(n, day + forget); i++) {
        if (i == day + forget) {
            ans -= 1;
            break;
        }
        ans = (ans + solve(i, delay, forget, n)) % mod;
    }

    return dp[day] = ans;
}

long long peopleAwareOfSecret(int n, int delay, int forget) {
    memset(dp, -1, sizeof(dp));
    return solve(1, delay, forget, n);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVA

### SOLUTION

static int MOD = 1000000007;
static int[] dp;

static int solve(int day, int delay, int forget, int n) {
    if (day + delay > n) return 1;
    if (dp[day] != -1) return dp[day];

    long ans = 1;

    for (int i = day + delay; i <= Math.min(n, day + forget); i++) {
        if (i == day + forget) {
            ans -= 1;
            break;
        }
        ans = (ans + solve(i, delay, forget, n)) % MOD;
    }

    return dp[day] = (int) ans;
}

public static long peopleAwareOfSecret(int n, int delay, int forget) {
    dp = new int[n + 2];
    Arrays.fill(dp, -1);
    return solve(1, delay, forget, n);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## C

### SOLUTION

long long dp[1001];
int MOD = 1000000007;

long long solve(int day, int delay, int forget, int n) {
    if (day + delay > n) return 1;
    if (dp[day] != -1) return dp[day];

    long long ans = 1;

    for (int i = day + delay; i <= (day + forget <= n ? day + forget : n); i++) {
        if (i == day + forget) {
            ans -= 1;
            break;
        }
        ans = (ans + solve(i, delay, forget, n)) % MOD;
    }

    return dp[day] = ans;
}

long long peopleAwareOfSecret(int n, int delay, int forget) {
    for (int i = 0; i <= n; i++) dp[i] = -1;
    return solve(1, delay, forget, n);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVASCRIPT

### SOLUTION

function peopleAwareOfSecret(n, delay, forget) {
    const MOD = 1000000007;
    const dp = Array(n + 2).fill(-1);

    function solve(day) {
        if (day + delay > n) return 1;
        if (dp[day] !== -1) return dp[day];

        let ans = 1;

        for (let i = day + delay; i <= Math.min(n, day + forget); i++) {
            if (i === day + forget) {
                ans -= 1;
                break;
            }
            ans = (ans + solve(i)) % MOD;
        }

        return dp[day] = ans;
    }

    return solve(1);
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## PYTHON

### SOLUTION

def people_aware_of_secret(n, delay, forget):
    MOD = 1000000007
    dp = [-1] * (n + 2)

    def solve(day):
        if day + delay > n:
            return 1
        if dp[day] != -1:
            return dp[day]

        ans = 1
        for i in range(day + delay, min(n, day + forget) + 1):
            if i == day + forget:
                ans -= 1
                break
            ans = (ans + solve(i)) % MOD

        dp[day] = ans
        return ans

    return solve(1)

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
