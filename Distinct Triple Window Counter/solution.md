## CPP

### SOLUTION

int countGoodSubstrings(string s) {
    int n = s.size();
    int ans = 0;

    for (int i = 0; i + 2 < n; i++) {
        if (s[i] != s[i + 1] &&
            s[i] != s[i + 2] &&
            s[i + 1] != s[i + 2]) {
            ans++;
        }
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

public static int countGoodSubstrings(String s) {
    int n = s.length();
    int ans = 0;

    for (int i = 0; i + 2 < n; i++) {
        char a = s.charAt(i);
        char b = s.charAt(i + 1);
        char c = s.charAt(i + 2);

        if (a != b && a != c && b != c) {
            ans++;
        }
    }
    return ans;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int countGoodSubstrings(char s[]) {
    int n = strlen(s);
    int ans = 0;

    for (int i = 0; i + 2 < n; i++) {
        if (s[i] != s[i + 1] &&
            s[i] != s[i + 2] &&
            s[i + 1] != s[i + 2]) {
            ans++;
        }
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

function countGoodSubstrings(s) {
  let ans = 0;

  for (let i = 0; i + 2 < s.length; i++) {
    if (s[i] !== s[i + 1] &&
        s[i] !== s[i + 2] &&
        s[i + 1] !== s[i + 2]) {
      ans++;
    }
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

def count_good_substrings(s):
    ans = 0
    n = len(s)

    for i in range(n - 2):
        if s[i] != s[i + 1] and s[i] != s[i + 2] and s[i + 1] != s[i + 2]:
            ans += 1
    return ans

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
