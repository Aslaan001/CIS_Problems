## CPP

### SOLUTION

int absMaxMinDiff(vector<int>& stars) {
    int mn = *min_element(stars.begin(), stars.end());
    int mx = *max_element(stars.begin(), stars.end());
    return mx - mn;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int absMaxMinDiff(int[] stars) {
    int mn = Arrays.stream(stars).min().getAsInt();
    int mx = Arrays.stream(stars).max().getAsInt();
    return mx - mn;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## C

### SOLUTION

int absMaxMinDiff(int stars[], int n) {
    int mn = stars[0], mx = stars[0];
    for (int i = 1; i < n; i++) {
        if (stars[i] < mn) mn = stars[i];
        if (stars[i] > mx) mx = stars[i];
    }
    return mx - mn;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function absMaxMinDiff(stars) {
    let mn = Math.min(...stars);
    let mx = Math.max(...stars);
    return mx - mn;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def absMaxMinDiff(stars):
    return max(stars) - min(stars)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
