## CPP

### SOLUTION

int goodSubstrings(string& s) {
    int count = 0;
    for (int i = 0; i + 2 < s.size(); i++) {
        if (s[i] != s[i+1] && s[i] != s[i+2] && s[i+1] != s[i+2])
            count++;
    }
    return count;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512

## JAVA

### SOLUTION

public static int goodSubstrings(String s) {
    int count = 0;
    for (int i = 0; i + 2 < s.length(); i++) {
        if (s.charAt(i) != s.charAt(i+1) && s.charAt(i) != s.charAt(i+2) && s.charAt(i+1) != s.charAt(i+2))
            count++;
    }
    return count;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## C

### SOLUTION

int goodSubstrings(char s[]) {
    int count = 0;
    for (int i = 0; s[i+2] != '\0'; i++) {
        if (s[i] != s[i+1] && s[i] != s[i+2] && s[i+1] != s[i+2])
            count++;
    }
    return count;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION

function goodSubstrings(s) {
  let count = 0;
  for (let i = 0; i + 2 < s.length; i++) {
    if (s[i] !== s[i+1] && s[i] !== s[i+2] && s[i+1] !== s[i+2]) count++;
  }
  return count;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def goodSubstrings(s):
    count = 0
    for i in range(len(s)-2):
        if s[i] != s[i+1] and s[i] != s[i+2] and s[i+1] != s[i+2]:
            count += 1
    return count

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
