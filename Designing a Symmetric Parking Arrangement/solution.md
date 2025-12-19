## CPP

### SOLUTION

long long countParkingWays(int n) {

    long long p = 1;

    for (int i = 0; i < n - 3; i++)
        p *= 4;

    long long res = 3LL * p * (3LL * n - 1);

    return res;
}


### METADATA

**TimeLimit**  
500

**MemoryLimit**  
64



## JAVA

### SOLUTION

public static long countParkingWays(int n) {

    long p = 1;

    for (int i = 0; i < n - 3; i++)
        p *= 4;

    long res = 3L * p * (3L * n - 1);

    return res;
}


### METADATA

**TimeLimit**  
500

**MemoryLimit**  
64
