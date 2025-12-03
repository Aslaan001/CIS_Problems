## CPP

### SOLUTION

long long minCost(const string &s) {
    long long res = 0;
    int n = s.length();
    for (int i = 1; i < n; ++i) {
        if (s[i - 1] != s[i]) res += min(i, n - i);
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

public static int minCost(String s) {
    int res = 0;
    int n = s.length();
    for (int i = 1; i < n; ++i) {
        if (s.charAt(i - 1) != s.charAt(i)) res += Math.min(i, n - i);
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

long long minCost(char s[]) {
    int n = strlen(s);
    long long res = 0;
    for (int i = 1; i < n; ++i) {
        if (s[i - 1] != s[i]) {
            int a = i;
            int b = n - i;
            res += (a < b) ? a : b;
        }
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

function minCost(s) {
  let res = 0;
  const n = s.length;
  for (let i = 1; i < n; ++i) {
    if (s[i - 1] !== s[i]) res += Math.min(i, n - i);
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

def min_cost(s):
    res = 0
    n = len(s)
    for i in range(1, n):
        if s[i - 1] != s[i]:
            res += min(i, n - i)
    return res

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
