## CPP

### SOLUTION

int minCollectionSpeed(vector<int>& cookies, int h) {
    int l = 1, r = 0;
    for(int c : cookies) r = max(r, c);
    while(l < r) {
        int mid = l + (r - l) / 2;
        long long hours = 0;
        for(int c : cookies)
            hours += (c + mid - 1) / mid; // ceil division
        if(hours > h) l = mid + 1;
        else r = mid;
    }
    return l;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512

## JAVA

### SOLUTION

public static int minCollectionSpeed(int[] cookies, int h) {
    int l = 1, r = 0;
    for(int c : cookies) r = Math.max(r, c);
    while(l < r) {
        int mid = l + (r - l) / 2;
        long hours = 0;
        for(int c : cookies)
            hours += (c + mid - 1) / mid; // ceil division
        if(hours > h) l = mid + 1;
        else r = mid;
    }
    return l;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## C

### SOLUTION

int max(int a, int b) { return a > b ? a : b; }

int minCollectionSpeed(int cookies[], int n, int h) {
    int l = 1, r = 0;
    for(int i = 0; i < n; i++) r = max(r, cookies[i]);
    while(l < r) {
        int mid = l + (r - l) / 2;
        long long hours = 0;
        for(int i = 0; i < n; i++)
            hours += (cookies[i] + mid - 1) / mid; // ceil division
        if(hours > h) l = mid + 1;
        else r = mid;
    }
    return l;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION

function minCollectionSpeed(cookies, h) {
  let l = 1, r = Math.max(...cookies);
  while (l < r) {
    let mid = Math.floor((l + r) / 2);
    let hours = 0;
    for (let c of cookies)
      hours += Math.ceil(c / mid);
    if (hours > h) l = mid + 1;
    else r = mid;
  }
  return l;
}


### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def minCollectionSpeed(cookies, h):
    l, r = 1, max(cookies)
    while l < r:
        mid = (l + r) // 2
        hours = sum((c + mid - 1) // mid for c in cookies)  # ceil division
        if hours > h:
            l = mid + 1
        else:
            r = mid
    return l

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
