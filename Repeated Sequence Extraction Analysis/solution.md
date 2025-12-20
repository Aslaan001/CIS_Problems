## CPP

### SOLUTION

int countTheRepetitions(string s1, long long n1, string s2, long long n2) {
    long long itr = 0, ans = 0;
    int l1 = s1.size(), l2 = s2.size();

    for (long long i = 0; i < n1; i++) {
        for (int j = 0; j < l1; j++) {
            if (s1[j] == s2[itr]) itr++;
            if (itr == l2) {
                itr = 0;
                ans++;
            }
        }
    }
    return ans / n2;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int countTheRepetitions(String s1, long n1, String s2, long n2) {
    long itr = 0, ans = 0;
    int l1 = s1.length(), l2 = s2.length();

    for (long i = 0; i < n1; i++) {
        for (int j = 0; j < l1; j++) {
            if (s1.charAt(j) == s2.charAt((int)itr)) itr++;
            if (itr == l2) {
                itr = 0;
                ans++;
            }
        }
    }
    return (int)(ans / n2);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int countTheRepetitions(char* s1, long long n1, char* s2, long long n2) {
    long long itr = 0, ans = 0;
    int l1 = strlen(s1), l2 = strlen(s2);

    for (long long i = 0; i < n1; i++) {
        for (int j = 0; j < l1; j++) {
            if (s1[j] == s2[itr]) itr++;
            if (itr == l2) {
                itr = 0;
                ans++;
            }
        }
    }
    return ans / n2;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function countTheRepetitions(s1, n1, s2, n2) {
    let itr = 0, ans = 0;
    const l1 = s1.length, l2 = s2.length;

    for (let i = 0; i < n1; i++) {
        for (let j = 0; j < l1; j++) {
            if (s1[j] === s2[itr]) itr++;
            if (itr === l2) {
                itr = 0;
                ans++;
            }
        }
    }
    return Math.floor(ans / n2);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def countTheRepetitions(s1, n1, s2, n2):
    itr = 0
    ans = 0
    l1 = len(s1)
    l2 = len(s2)

    for _ in range(n1):
        for j in range(l1):
            if s1[j] == s2[itr]:
                itr += 1
            if itr == l2:
                itr = 0
                ans += 1

    return ans // n2

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
