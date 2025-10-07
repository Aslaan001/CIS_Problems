## CPP

### SOLUTION

char nextRune(vector<char>& letters, char target) {
    int n = letters.size();
    int l = 0, r = n - 1;
    while (l <= r) {
        int mid = l + (r - l) / 2;
        if (letters[mid] <= target)
            l = mid + 1;
        else
            r = mid - 1;
    }
    return letters[l % n];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512

## JAVA

### SOLUTION

public static char nextRune(char[] letters, char target) {
        int n = letters.length;
        int l = 0, r = n - 1;
        while (l <= r) {
            int mid = l + (r - l) / 2;
            if (letters[mid] <= target)
                l = mid + 1;
            else
                r = mid - 1;
        }
        return letters[l % n]; // wraps around if needed
    }

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## C

### SOLUTION

char nextRune(int n, char letters[], char target) {
    int l = 0, r = n - 1;
    while (l <= r) {
        int mid = l + (r - l) / 2;
        if (letters[mid] <= target)
            l = mid + 1;
        else
            r = mid - 1;
    }
    return letters[l % n];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION

function nextRune(letters, target) {
  let n = letters.length;
  let l = 0, r = n - 1;
  while (l <= r) {
    let mid = Math.floor((l + r) / 2);
    if (letters[mid] <= target) l = mid + 1;
    else r = mid - 1;
  }
  return letters[l % n];
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def nextRune(letters, target):
    l, r = 0, len(letters) - 1
    while l <= r:
        mid = (l + r) // 2
        if letters[mid] <= target:
            l = mid + 1
        else:
            r = mid - 1
    return letters[l % len(letters)]

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
