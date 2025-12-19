## CPP

### SOLUTION

long long minMovesToReach(long long a, long long b) {

    long long ans = (long long)1e18;

    for (long long m = 1; m <= 100000; ++m) {
        long long moves =
            (a + m - 1) / m +
            (b + m - 1) / m +
            m - 1;
        ans = min(ans, moves);
    }

    return ans;
}


### METADATA

**TimeLimit** 
2000

**MemoryLimit**  
256



## JAVA

### SOLUTION

public static long minMovesToReach(long a, long b) {

    long ans = Long.MAX_VALUE;

    for (long m = 1; m <= 100000; m++) {
        long moves =
            (a + m - 1) / m +
            (b + m - 1) / m +
            m - 1;
        ans = Math.min(ans, moves);
    }

    return ans;
}


### METADATA

**TimeLimit** 
2000

**MemoryLimit**  
256
