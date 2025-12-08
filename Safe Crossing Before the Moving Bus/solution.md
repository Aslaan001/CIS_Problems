## CPP

### SOLUTION

double crossTime(int n, long long w, long long v, long long u, const vector<pair<long long,long long>>& poly) {
    double l = 1e18, r = 0;
    for (int i = 0; i < n; i++) {
        double x = poly[i].first;
        double y = poly[i].second;
        double val = x - y / (double)u * v;
        l = min(l, val);
        r = max(r, val);
    }
    return w / (double)u + (l < 0 ? r / (double)v : 0.0);
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512

## JAVA

### SOLUTION

public static double crossTime(int n, long w, long v, long u, long[][] poly) {
    double l = 1e18, r = 0;
    for (int i = 0; i < n; i++) {
        double x = poly[i][0];
        double y = poly[i][1];
        double val = x - y / (double)u * v;
        l = Math.min(l, val);
        r = Math.max(r, val);
    }
    return w / (double)u + ((l < 0) ? r / (double)v : 0.0);
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**  
512
