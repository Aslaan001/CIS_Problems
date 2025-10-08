## CPP

### SOLUTION

int relicSearch(vector<int>& relics, int key) {
    int low = 0, high = 1;
    while (high < relics.size() && relics[high] < key)
        low = high, high *= 2;
    high = min(high, (int)relics.size() - 1);
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (relics[mid] == key) return mid;
        else if (relics[mid] < key) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512

## JAVA

### SOLUTION

public static int relicSearch(int[] relics, int key) {
    int low = 0, high = 1;
    while (high < relics.length && relics[high] < key){
        low = high;
        high *= 2;
    
    }
    high = Math.min(high, relics.length - 1);
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (relics[mid] == key) return mid;
        else if (relics[mid] < key) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## C

### SOLUTION

int min(int a, int b) { return a < b ? a : b; }

int relicSearch(int relics[], int n, int key) {
    int low = 0, high = 1;
    while (high < n && relics[high] < key)
        low = high, high *= 2;
    if (high >= n) high = n - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (relics[mid] == key) return mid;
        else if (relics[mid] < key) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION

function relicSearch(relics, key) {
    let low = 0, high = 1;
    while (high < relics.length && relics[high] < key)
        low = high, high *= 2;
    high = Math.min(high, relics.length - 1);
    while (low <= high) {
        let mid = Math.floor((low + high) / 2);
        if (relics[mid] === key) return mid;
        else if (relics[mid] < key) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def relicSearch(relics, key):
    low, high = 0, 1
    while high < len(relics) and relics[high] < key:
        low = high
        high *= 2
    high = min(high, len(relics) - 1)
    while low <= high:
        mid = (low + high) // 2
        if relics[mid] == key:
            return mid
        elif relics[mid] < key:
            low = mid + 1
        else:
            high = mid - 1
    return -1

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
