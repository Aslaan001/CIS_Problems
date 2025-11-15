## CPP

### SOLUTION

// custom gcd (works on ANY C++ version)
int mygcd(int a, int b) {
    return b == 0 ? a : mygcd(b, a % b);
}

string gcdString(const string &a, const string &b) {
    if (a + b != b + a) return "";s
    return a.substr(0, mygcd(a.size(), b.size()));
}

string solve(const string &str1, const string &str2) {
    return gcdString(str1, str2);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION

 static String gcdString(String a, String b) {
        if (!(a + b).equals(b + a)) return "";
        int g = gcd(a.length(), b.length());
        return a.substring(0, g);
    }

    static int gcd(int a, int b) {
        while (b != 0) {
            int t = a % b;
            a = b;
            b = t;
        }
        return a;
    }

    static String solve(String str1, String str2) {
        return gcdString(str1, str2);
    }

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION

int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}

char* gcdString(const char* a, const char* b) {
    int lenA = strlen(a);
    int lenB = strlen(b);

    char *ab = malloc(lenA + lenB + 1);
    char *ba = malloc(lenA + lenB + 1);

    strcpy(ab, a);
    strcat(ab, b);

    strcpy(ba, b);
    strcat(ba, a);

    if (strcmp(ab, ba) != 0) {
        free(ab); free(ba);
        char *empty = malloc(1);
        empty[0] = '\0';
        return empty;
    }

    free(ab); free(ba);

    int g = gcd(lenA, lenB);
    char *res = malloc(g + 1);
    strncpy(res, a, g);
    res[g] = '\0';
    return res;
}

char* solve(const char* str1, const char* str2) {
    return gcdString(str1, str2);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION

function gcd(a, b) {
    while (b !== 0) {
        const t = a % b;
        a = b;
        b = t;
    }
    return a;
}

function gcdString(a, b) {
    if (a + b !== b + a) return "";
    return a.slice(0, gcd(a.length, b.length));
}

function solve(str1, str2) {
    return gcdString(str1, str2);
}

### METADATA

**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION

def gcd(a, b):
    while b:
        a, b = b, a % b
    return a

def gcdString(a, b):
    if a + b != b + a:
        return ""
    g = gcd(len(a), len(b))
    return a[:g]

def solve(str1, str2):
    return gcdString(str1, str2)


### METADATA

**TimeLimit**
1000

**MemoryLimit**
128
